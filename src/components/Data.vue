<template>
    <div>
        <h2>Without Composition API {{fname}}</h2>
        <h2>Using Ref {{firstName}}</h2>
        <h2>Using Ref {{greet}}</h2>
        <h2>Using Reactive Approach {{first_name}}  {{last_name}}</h2>
    </div>
</template>

<script>
import {ref, reactive,toRefs} from 'vue';

    export default {
        name:'DataApp',
        setup(){
            const firstName =ref('Eswara');
            firstName.value ='SadaShiva';
            const greet = `Welcome ${firstName.value}`
            const state = reactive({
                first_name:'Sarveswara',
                last_name:'Manjunadha'
            })
            return{
                greet,
                firstName,
                ...toRefs(state)
            }
        },

       data(){
        return{
            fname:'Sai Baba'
        }
       }
    }
</script>

<style scoped>

</style>