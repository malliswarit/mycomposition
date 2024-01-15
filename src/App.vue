<template>
<h1>Composition API</h1>

<DataApp />
<DemoOne />
<DemoTwo />
<DemoThree/>
<VModel />
<ComputedApp />
<WatcherApp />
<ProvideApp/>
<PersonApp />
</template>


<script>

import DataApp from "./components/Data.vue";
import DemoOne from "./components/DemoOne.vue";
import DemoTwo from "./components/DemoTwo.vue";
import DemoThree from "./components/DemoThree.vue";
import VModel from "./components/VModel.vue";
import ComputedApp from './components/Computed.vue';
import WatcherApp from "./components/Watch.vue";
import ProvideApp from "./components/Provide.vue";
import PersonApp from "./components/Person.vue"
export default {
  name: 'App',
 
  components:{
    DataApp,
    DemoOne,
    DemoTwo,
    DemoThree,
    VModel,
    ComputedApp,
    WatcherApp,
    ProvideApp,
    PersonApp
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
