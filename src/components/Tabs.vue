<template>
  <div class="tabs flex-center-between">
    <button
      @click="$emit('handle', index + 1)"
      v-for="(item, index) in tabs"
      :key="index"
      class="tabs__item"
    >
      <icon-base :name="item.icon" />
      <span>{{ item.name }}</span>
    </button>
  </div>
</template>

<script>
import IconBase from "./common/IconBase.vue";
export default {
  components: { IconBase },
  data() {
    return {
      tabs: [
        {
          name: "След. Урок",
          icon: "next",
        },
        {
          name: "Отменить",
          icon: "bookmark_added",
        },
        {
          name: "Коментарии",
          icon: "chat",
        },
        {
          name: "Все уроки",
          icon: "all_lesson",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.tabs__item {
  width: 80px;
  height: 80px;
  font-weight: 500;
  font-size: 12px;
  line-height: 22px;
  text-align: center;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 1px;
  span {
    display: block;
  }
}
</style>