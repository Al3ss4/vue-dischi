<template>
  <div class="container">
    <div class="row logo align-items-center">
      <div class="col-12">
        <img src="@/assets/logo.png" alt="spotify-logo" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "headerComponent",
};
</script>

<style lang="scss" scoped>
@import '@/style/utility';

.logo {
  background-color: $bg-header;
  height: 80px;

  img {
    width: 5%;
  }
}
</style>