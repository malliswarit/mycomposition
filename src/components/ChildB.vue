<template>
    <div>
        <ChildC />
    </div>
</template>

<script>
import ChildC from "./ChildC.vue";

    export default {
        name:'ChildB',
        components:{
            ChildC
        }
    }
</script>

<style scoped>

</style>