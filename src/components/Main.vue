<template>

  <main class="container">
    
      <div v-if="element.length > 0 " class="row justify-content-center" >
        <SongItem v-for="song in element " :key="song" :singleCd="song" 
        class="col col-md-6 col-xl-4 mx-2 "/>
        
      </div>
      <div v-else>
        
          </div>  
   
  </main>

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
@import '@/style/utility';
main{
  background-color: $bg-main;
}

</style>