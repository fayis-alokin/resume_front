<template>
  <div class="back-main">
    <div class="back-link">
      <a href=""> - Back to list</a>
    </div>
    <div class="back-content">
      <h4>Create resume content</h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'backmenu',
  props: {
    msg: String,
    
  },
  
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style>
.back-main{
  background-color: rgb(212, 218, 218);
  display: flex;
  flex-direction: column;

}
.back-link a{
  text-decoration: none;
  color: rgb(36, 128, 97);

}
.back-link{
  padding: 10px;
}
.back-content{
  padding: 9px 10px;
}
h4{
  font-family: sans-serif;
}
</style>

