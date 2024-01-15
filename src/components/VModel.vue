<template>
    <div>
        <input type='text' v-model='fname' /> <h1>{{fname}}</h1>
        <input type='text' v-model='lname' /> <h1>{{lname}}</h1>
        <input type='text' v-model='fullName' /> <h1>{{fullName}}</h1>

   

    </div>
</template>

<script>
import { reactive ,ref,toRefs} from 'vue';
    export default {
        name:'VModel',
        
        data(){
            return{
                fname:''
            }
        },   

        setup(){
            const lname = ref('');
            const state = reactive({
                fullName:''
            })
            return{
                lname,
                ...toRefs(state)
            }
        },

    }
</script>

<style scoped>

</style>