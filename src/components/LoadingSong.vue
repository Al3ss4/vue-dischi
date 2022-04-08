<template>
  <h2 class="loading fw-bold">
    <p>{{ label }}</p>
  </h2>
</template>

<script>
export default {
  name: "LoadingSong",
  props: {
    label: String,
  },
};
</script>

<style lang="scss" scoped>

.loading
{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    color: black;
}
</style>