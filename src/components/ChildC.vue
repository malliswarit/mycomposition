<template>
    <div>
        <h2>UserName using normal Provide {{userName}}</h2>
         <h2>UserName using composition API Provide {{childUserName}}</h2>
         <h2>{{childCount}}</h2>
           <h2>{{childfullName}}</h2>
        <button @click="incrementCount">Increment From Child</button>
    </div>
</template>

<script>
import{inject} from 'vue';

    export default {
        name:'ChildC',
        inject:['userName'],
        setup(){
           const childUserName = inject('c_userName','DefaultValue');
           const childCount = inject('c_count',0);
           const childfullName = inject('c_fullName',{})
           const incrementCount = inject('incrementCount')
           return{
            childUserName,
            childCount,
            childfullName,
            incrementCount
           }
        }
    
    }
</script>

<style scoped>

</style>