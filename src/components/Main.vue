<template>
  <div class="container">
    <div class="row">
      <div v-if="element.length > 0 " class="col col-md-6 col-xl-4">
        <SongItem :singleCd="element[0]" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import SongItem from '@/components/SongItem.vue'

export default {
name: 'mainComponent',
data(){
  return{
    element:[]
  }
},
props:{
  album: String
},
components:{
  SongItem
},
mounted(){
  this.loadAlbum();
},
methods:{
loadAlbum(){
  axios.get(this.album).then(
    (response)=>{
      //console.log(response);
      if (response.status === 200){
        this.element = response.data.response;
        console.log(this.element[0]);
      }
    }
  )
}
}
}

</script>

<style lang="scss" scoped>

</style>