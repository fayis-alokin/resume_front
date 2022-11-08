<template>
    <div class="list-navbar">
        <h2>All Resumes</h2>
        
    </div>
    <div class="list-main">
        
        <div class="list-left">whegr</div>
        <div class="list-right">
            <div class="list-heading">
                <h2>Resume</h2>
            </div>
            <div class="line"></div>
            <div class="list-search-main">
                <div class="list-search-left">
                    <input type="text" placeholder="Search by name or email">
                </div>
                <div class="list-search-right">
                    <a href="">+ Add new resume</a>
                </div>
            </div>
            <table>
                <tr class="table-heading">
                    <th>Name</th>
                    <th>Phone</th>
                    <th>Email</th>
                    <th>Applied on</th>
                </tr>
                <tr class="table-datamodel">
                    <td>Fayis</td>
                    <td>645646657676</td>
                    <td>hgyugy@gmail.com</td>
                    <td>29-04-2002</td>
                </tr>
                <tr v-for="item in list" :key="item.basic_details_id">
                    <div v-for="i in item" class="data">
                        <td>{{i.name}}</td>
                        <td>{{i.phone}}</td>
                        <td>{{i.email}}</td>
                        <td>{{i.date_applied}}</td>
                    </div>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>

 import axios from 'axios'
// import VueAxios from 'vue-axios'
// Vue.use(VueAxios,axios)


export default{
    name:'list_navbar',
    data(){
        return {
            list:[]
        }
    },
    mounted(){
        axios.get('http://127.0.0.1:8000/get_allprimary')
        .then((resp)=> {
            this.list = resp.data
            console.log(resp.data)
        })
    }
   

}

</script>


<style>
.list-navbar{
    background-color: black;
    color: white;
    padding: 20px;
}
.list-main{
    display: flex;
}
.list-right{
    background-color: rgb(241, 241, 241);
    width: 85%;
}
.list-left{
    background-color: aqua;
    width: 15%;
}
.list-heading{
    padding: 10px;
}
.line{
    height: 1px;
    background-color: rgb(151, 146, 146);
    width: 99%;
    margin-left: 10px;
}
.list-search-main{
    display: flex;
    margin: 10px;
}
.list-search-left{
    width: 50%;
}
.list-search-right{
    width: 50%;
    padding-left: 30%;
    padding-top: 10px;
}
.list-search-right a{
    text-decoration: none;
}
input{
    width: 60%;
    height: 5vh;
    padding: 20px;
    border-radius: 5px;
    border: 1px solid rgb(151, 146, 146);
    background-color: rgb(241, 241, 241);
}
input:focus{
    border: 1px solid rgb(151, 146, 146);
    background-color: rgb(241, 241, 241);
}
table{
    padding: 50px;

}
th{
    width: 400px;
    background-color: black;
    color: aliceblue;
    text-align: center;
    vertical-align: middle;
    padding-bottom: 10px;

}
.data td{
    text-align: center;
    padding-left: 20px;
    
}
.table-datas{
    padding-left: 10px;
}
table{
    background-color: burlywood;
}
.data{
   
    background-color: aquamarine;
    justify-content: space-between ;
    
}

</style>













