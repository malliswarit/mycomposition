<template>
    <div>
        <h1>Using Reactive Approach writing Methods</h1>
        <h2>{{name}}</h2>
        <button @click="updateName">Update Name using Reactive</button>
    </div>
</template>

<script>
import {reactive, toRefs} from 'vue';

    export default {
        name:'DemoThree',
        setup(){
            const state= reactive({
                name:'Amma Bhavani'
            })

            function updateName(){
                state.name = 'Sarveswari'
            }

            return{
                ...toRefs(state),
                updateName
            }
        }
    }
</script>

<style scoped>

</style>