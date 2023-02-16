<template>
  <h3 class="title">{{ title }}</h3>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: () => "",
    },
  },
};
</script>

<style lang="scss" scoped>
.title {
  font-weight: 700;
  font-size: 20px;
  line-height: 32px;
  color: rgba(255, 255, 255, 0.9);
}
</style>