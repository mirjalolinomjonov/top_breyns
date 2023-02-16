<template>
  <p class="paragraph" :style="{ color: color }">{{ paragraph }}</p>
</template>

<script>
export default {
  props: {
    paragraph: {
      type: String,
      default: () => "",
    },
    color: {
      type: String,
      default: () => "",
    },
  },
};
</script>

<style lang="scss" scoped>
.paragraph {
  font-weight: 500;
  font-size: 16px;
  line-height: 22px;
}
</style>