<template>
  <div>
      <img :src="singleCd.poster" :alt="singleCd.genre"/>
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
</style>