<template>
    <div :class="open ? 'acc open':'acc'" @click="$emit('toggleOpen',index)">
        <div class="acc-title">{{acc.title}}</div>
        <div class="acc-content" >
            <div class="input-label">
               <p>{{acc.name}}</p>
               <p>{{acc.email}}</p>
               <p>{{acc.phone}}</p>
               <p>{{acc.url}}</p>
            </div>
            <div class="input-field">
                <input type="text">
                <input type="text">
                <input type="text">
                <input type="text">
            </div>

        </div>
        
    </div>


</template>

<script>

import inputslabel from './inputs_label.vue'
import input_field from './input_field.vue'
export default{
    name:'accordion',
    props:['acc','index','open'],
    components:{
        inputslabel,
        input_field
    }
}

</script>

<style>
input{
    width: 80%;
}

</style>