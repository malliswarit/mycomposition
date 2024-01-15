<template>
    <div>
        <button @click="updateName">Update Name</button>
        <h2>{{name}}</h2>
        
    </div>
</template>

<script>
    export default {
        name:'DemoOne',
        data(){
            return{
                name:'Eswara'
            }
        },
        methods:{
            updateName(){
                this.name='Parameswara'
            }
        }
    }
</script>

<style scoped>

</style>