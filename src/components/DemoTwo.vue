<template>
    <div>
        <h2>Using Ref updating using methods</h2>
        <button @click="updateName">Update Name Using Ref</button>
        <h3>{{name}}</h3>
    </div>
</template>

<script>
import{ref} from 'vue';

    export default {
        name:'DemoTwo',
        setup(){
            const name = ref('SriKrishna');
            function updateName(){
                name.value='Govinda'
            }

            return{
                name, updateName
            }
        }
    }
</script>

<style scoped>

</style>