<template>
    <div>
    <input type='text' v-model='fname'/>
      <input type='text' v-model='reffname'/>
          <input type='text' v-model='reflname'/>
        <input type='text' v-model='reactivefname'/>
         <input type='text' v-model='reactivelname'/>
         <input type='text' v-model='options.heroName'/>
        <h1>{{fname}}</h1>
        <h1>{{reffname}}</h1>
        <h1>{{reflname}}</h1>
        <h1>{{reactivefname}}</h1>
        <h1>{{reactivelname}}</h1>
         <h1>{{options.heroName}}</h1>
    </div>
</template>

<script>
import{ref,reactive,toRefs,watch} from 'vue'
import _ from 'lodash'
    export default {
        name:'WatcherApp',
        setup(){
            const reffname = ref('');
             const reflname = ref('');
            const state = reactive({
                reactivefname:'',
                reactivelname:'',
                options:{
                    heroName:''
                }
            })

            watch(() => { return{...state}}, function(newValue,oldValue){
                 console.log(newValue.reactivefname+"Using Reactive")
                console.log(oldValue.reactivefname+"Using Reactive")
                  console.log(newValue.reactivelname+"Using Reactive")
                console.log(oldValue.reactivelname+"Using Reactive")
            },{deep:true})

            watch(() => _.cloneDeep(state.options), function(newValue,oldValue){
                console.log(newValue.heroName)
                 console.log(oldValue.heroName)
            },{deep:true})
            watch([reffname,reflname], function(newValues,oldValues){
                  console.log(newValues[0]+"Using Ref")
                console.log(oldValues[0]+"Using Ref")
                console.log(newValues[1]+"Using Ref")
                console.log(oldValues[1]+"Using Ref")
            })

            return{
                ...toRefs(state),
                reffname,   reflname
            }
        },
        data(){
           return{
            fname:''
           }
        },
        watch:{
            fname(newValue,oldValue){
                console.log(newValue+"Normal")
                console.log(oldValue+"Normal")
            }
        }
    }
</script>

<style scoped>

</style>