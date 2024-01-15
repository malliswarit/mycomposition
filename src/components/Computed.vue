<template>
    <div>
        <h1>Normal{{getfullName}}</h1>
         <h1>Using Ref{{ReffullName}}</h1>
          <h1>Using Reactive{{ReactiveFullName}}</h1>
    </div>
</template>

<script>
    import{ref,computed, reactive,toRefs} from 'vue';

    export default {
        name:'ComputedApp',
        setup(){
            const fname = ref('Eswara')
            const lname = ref('Sarveswara')
        const ReffullName = computed(function(){
            return `${fname.value} ${lname.value}`
        })

        const state = reactive({
            fname:'Amma',
            lname:'Bhavani'
        })

        const ReactiveFullName = computed(function(){
            return `${state.fname} ${state.lname}`
        })

        return{ ReffullName, ...toRefs(state), ReactiveFullName}

        },
        data(){
            return{
                fname:'Sai',
                lname:'Baba'
            }
        },
        computed:{
            getfullName(){
                return this.fname+this.lname
            }
        }
    }
</script>

<style scoped>

</style>