<template>
  <div id="app">
    <Header />
    <Main :album='urlMusic'/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data(){
    return{
      urlMusic:'https://flynn.boolean.careers/exercises/api/array/music'
    }
  }
};
</script>

<style lang="scss">
@import '@/style/utility';
@import '@/style/general';


</style>
