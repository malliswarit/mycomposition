<template>
    <div>
        <h1>Iam child component</h1>
        <h5>{{firstName}}</h5>
        <h5>{{lastName}}</h5>
        <h5>{{fullName}}</h5>
        <button @click="sendEvent">Call Parent</button>
    </div>
</template>

<script>

    export default {
        name:"PersonGreeting",
        props:['firstName','lastName','fullName'],
        setup(props,context){
            function sendEvent(){
                context.emit('callHeroes', 'Jai Bhavani')
            }

            return{
                sendEvent
            }
        },
        emits:['callHeroes']
    }
</script>

<style scoped>

</style>