<template>
    <div>
        <button @click="incrementCount">UpdateCount</button>
        <ChildA />
    </div>
</template>

<script>
import ChildA from "./ChildA.vue";
    import {provide,ref,reactive,toRefs} from 'vue';

    export default {
        name:'ProvideApp',
        
        setup(){

            const count = ref(0);
            function incrementCount(){
                count.value++
            }
            const state = reactive({
                fname:'Sai', lname:'Baba'
            })
            provide('c_count',count)
            provide('c_fullName',state.fname+state.lname)
            provide('c_userName','codeevolution')
            provide('incrementCount', incrementCount)
            return{
                ...toRefs(state),
                count,
                incrementCount
            }
        },
        components:{
            ChildA
        },
        data(){
            return{
                userName:'Vishwas'
            }
        },

        provide(){
            return{
                userName:this.userName
            }
        }
    }
</script>

<style scoped>

</style>