<template>
    <div>
    <input type='text'  v-model='firstName'/>
     <input type='text' v-model='lastName' />
    
<PersonGreeting  :firstName='firstName' :lastName='lastName' :fullName='fullName'  @callHeroes="callHeroes"/>
    </div>
</template>

<script>
import PersonGreeting from './PersonGreeting.vue'
import {reactive,toRefs,computed} from 'vue';

    export default {
        name:'PersonApp',
        components:{
            PersonGreeting
        },
        setup(){
            const state = reactive({
                firstName:'',
                lastName:''
            })

            const fullName = computed(() => {
                return(
                   ` ${state.firstName} ${state.lastName}`
                )
            })

            function callHeroes(value){
            console.log(value)
            }

            return{
                ...toRefs(state),
                fullName,
                callHeroes
            }
        }
    }
</script>

<style scoped>

</style>