<template>
  <aside class="aside">
    <div class="list-wrap">
      <ul class="list" v-for="(item, index) in lesson" :key="index">
        <h3 class="list__title">{{ item.title }}</h3>
        <li
          v-for="(lesson, index) in item.child"
          :key="index"
          class="list__item"
          :class="{ active: lesson?.currentLesson }"
        >
          <h4 class="flex-center-between">
            <span> {{ index + 1 }}. {{ lesson.name }} </span>
            <span
              class="
                font-semibold
                text-[15px]
                leading-[22px]
                text-[#ffffff4d]
                whitespace-nowrap
              "
            >
              {{ lesson.time }} min
            </span>
          </h4>
          <p
            v-if="lesson?.description && lesson?.currentLesson"
            class="list__item-description"
          >
            {{ lesson.description }}
          </p>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script>
export default {
  props: {
    lesson: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.aside {
  height: 603px;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    height: 40px;
    width: 100%;
    // background: linear-gradient(180deg, rgba(8, 8, 8, 0) 0%,  #1E1E1E 100%);
    background: linear-gradient(180deg, rgba(8, 8, 8, 0) 0%, rgba(8, 8, 8, 0.83) 63.54%, #080808 100%);
  }
}
.list-wrap {
  max-height: 100%;
  overflow-y: auto;
}
.list {
  &:not(:last-child) {
    margin-bottom: 1rem;
  }
  // list__title
  &__title {
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.04);
    border-radius: 10px;
    padding: 10px 24px;
    font-weight: 600;
    font-size: 18px;
    line-height: 16px;
    letter-spacing: 0.15px;
    color: rgba(255, 255, 255, 0.9);
  }
  // list__item
  &__item {
    font-weight: 500;
    font-size: 18px;
    line-height: 22px;
    color: rgba(255, 255, 255, 0.9);
    padding: 21px 24px;
    &:not(:last-child) {
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }
    &-description {
      font-size: 16px;
      line-height: 22px;
      color: rgba(255, 255, 255, 0.5);
      margin-top: 1rem;
    }
    &.active {
      border-radius: 10px;
      border: 1px solid rgba(255, 255, 255, 0.04);
      background: rgba(255, 255, 255, 0.06);
    }
  }

  // SCROLLBAR
  &::-webkit-scrollbar-track {
    background: #222;
  }

  &::-webkit-scrollbar {
    width: 7px;
  }

  &::-webkit-scrollbar-thumb {
    background: #ffffff14;
    border-radius: 3.5px;
    transition: 0.3s ease-in-out;
  }

  &::-webkit-scrollbar-thumb:hover {
    background: rgba(255, 255, 255, 0.5);
  }
}
</style>