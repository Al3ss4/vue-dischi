<template>
  <div class="container">
    main
  </div>
</template>

<script>
import axios from 'axios'
export default {
name: 'mainComponent',
props:{
  album: String
},
mounted(){
  this.loadAlbum();
},
methods:{
loadAlbum(){
  axios.get(this.album).then(
    (response)=>{
      console.log(response);
    }
  )
}
}
}

</script>

<style lang="scss" scoped>

</style>