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
@import "@/style/utility";
@import "@/style/general";

.logo {
  background-color: #2e3a46;
  height: 80px;

  img {
    width: 5%;
  }
}
</style>