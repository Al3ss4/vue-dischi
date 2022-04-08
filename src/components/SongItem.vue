<template>
  <div class="text-center album mt-5">
    <img class="mb-2 w-100" :src="singleCd.poster" :alt="singleCd.genre" />
    <h3 class="mt-3">{{ singleCd.title }}</h3>
    <div class="description mt-3">
      <p>{{ singleCd.author }}</p>
      <p>{{ singleCd.year }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "songItem",
  props: {
    singleCd: Object,
  },
};
</script>

<style lang="scss" scoped>
.album {
  background-color: #2e3a46;
  padding: 20px;
  width: 250px;
  
  .description {
    line-height: 0;
    p{
        font-size: 1rem;
    }
  }
}
</style>