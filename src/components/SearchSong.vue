<template>
  <div>
      <input type="text" placeholder="Search"
      v-model.trim="genreSong"
      @keyup.enter="search" />
      <button @click.prevent="search">Search</button>
  </div>
</template>

<script>
export default {
name:'SearchSong',
data(){
    return{
        genreSong:''
    }
},
methods:{
    search(){
        console.log('SearchSong testo', this.genreSong);
        this.$emit('SearchSong', this.genreSong);
    }
}
}
</script>

<style>

</style>