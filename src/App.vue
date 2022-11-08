<template>
  
  <navbar/>
  <backmenu/>
  <div class="accord">
    <accordion v-for="(acc,i) in accord" :acc="acc" :index="i" :key="i" :open="acc.open" @toggleOpen="toggleOpen"/>

  </div>
  
</template>

<script>
import accordion from './components/accordion.vue'
import backmenu from './components/backmenu.vue'
import navbar from './components/navbar.vue'

export default {
  name: 'sApp',
  components: {
    navbar,
    backmenu,
    accordion
  },
  data(){
    return{
      accord:[
        {
          title:"Add Primary details",
          name:"Name",
          email:"Email",
          phone:"Phone",
          DOB:"Date of Birth",
          url:"Image",
          summary:"Summary",
          open:true
        },
        {
          title:"Add Address details",
          name:"House Name",
          email:"Street",
          phone:"Country",
          DOB:"Date of Birth",
          open:false
        },
        {
          title:"Add Education details",
          name:"House Name",
          email:"Street",
          phone:"Country",
          DOB:"Date of Birth",
          
          open:false
        }
      ]
    }
  },
  methods:{
    toggleOpen: function (index) {
      this.accord.map((acc,i)=> {
        if (index === i){
          acc.open = !acc.open;
        // }else{
        //   acc.open = false
        }
        return acc

      })
      
    }
  }
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.acc{
  display: block;
  margin: 15px auto;
  width: 100%;
  max-width: 768px;
  padding: 15px;
  border-radius: 7px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}
.acc .acc-title{
  position: relative;
  color: #3c3c3c;
  transition: all 0.4s linear;
  height: 30px;
}
.acc .acc-title::after{
  content: " ";
  position: absolute;
  top: 50%;
  transform: translateY(-50%);

  transition: all 0.2s linear;
}
.acc .acc-content{
  color: #3c3c3c;
  display: none;
  font-size: 18px;
  overflow-y: hidden;
  
}
.acc.open .acc-title{
  margin-bottom: 10px;
}
.acc.open .acc-title::after{
  transform: translateY(-50%);
 
}
.acc.open .acc-content{
  display: flex;
  max-height: 1000px;
}
</style>
