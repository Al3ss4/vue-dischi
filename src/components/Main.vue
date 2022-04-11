<template>
  <main class="container">
    <div class="row text-center  ">
      <div class="col mt-4">
        <SearchSong @SearchSong ='filterItem'/>
      </div>
    </div>

    <div v-if= "!loadElement" class="row justify-content-center">
      <SongItem
        v-for="song in filtGenre "
        :key="song"
        :singleCd="song"
        class="col col-md-6 col-xl-4 mx-2"
      />
    </div>
    <LoadingSong v-else label="Caricamento" />
  </main>
</template>

<script>
import axios from "axios";
import SongItem from "@/components/SongItem.vue";
import LoadingSong from "@/components/LoadingSong.vue";
import SearchSong from "@/components/SearchSong.vue";

export default {
  name: "mainComponent",
  data() {
    return {
      element: [],
      searchList:''
    };
  },
  props: {
    album: String,
  },
  computed:{
    loadElement(){
      return this.element.length === 0;
    },
    filtGenre(){
      if (this.searchList.length === 0){
        return this.element
      }
      return this.element.filter((item)=> item.genre.toLowerCase().includes(this.searchList.toLowerCase()))
    }
  },
  components: {
    SongItem,
    LoadingSong,
    SearchSong,
  },
  mounted() {
    this.loadAlbum();
  },
  methods: {
    loadAlbum() {
      axios.get(this.album).then((response) => {
        //console.log(response);
        if (response.status === 200) {
          this.element = response.data.response;
          //console.log(this.element[0]);
        }
      });
    },
    filterItem(searchList){
      this.searchList = searchList;
      console.log(searchList);
    }
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/utility";
main {
  background-color: $bg-main;
}
</style>