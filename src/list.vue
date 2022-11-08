<template>
   <Suspense>
    <list_navbar/>
   </Suspense>

</template>

<script>
import list_navbar from './components/Listing/list_navbar.vue'
export default{
    name:'App',
    components:{
        list_navbar
    }
}

</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

</style>