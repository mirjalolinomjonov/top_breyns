<template>
  <aside class="py-3 relative">
    <span
      class="
        hidden
        md:inline-block
        absolute
        top-3
        left-1/2
        -translate-x-1/2
        cursor-pointer
        h-[6px]
        w-12
        bg-[#ffffff14]
        rounded-md
      "
    ></span>
    <h2
      class="
        hidden
        md:block
        text-[#ffffffe6] text-lg
        leading-6
        font-bold
        mt-[10px]
        mb-4
        ml-4
      "
    >
      Программа
    </h2>
    <div class="aside">
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
    </div>
    <!-- STATUS CARD -->
    <div class="grid grid-cols-2 gap-6 mt-12">
      <Status
        v-for="(item, index) in status"
        :key="index"
        v-bind="{
          img: item?.img,
          currentLesson: item?.currentLesson,
          countLesson: item?.countLesson,
          lessonForToday: item?.lessonForToday,
          title: item?.title,
        }"
      />
    </div>
  </aside>
</template>

<script>
import Status from "./common/Status.vue";
export default {
  components: {
    Status,
  },
  props: {
    lesson: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      status: [
        {
          img: "@/static/images/user2.png",
          title: "Даниэль Пинк",
        },
        {
          currentLesson: 13,
          countLesson: 20,
          title: "Уроков завершено",
        },
        {
          lessonForToday: 2,
          title: "Урока за сегодня",
        },
        {
          img: "@/static/images/user2.png",
          title: "Хасан Ш.",
        },
      ],
    };
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
    background: linear-gradient(
      180deg,
      rgba(8, 8, 8, 0) 0%,
      rgba(8, 8, 8, 0.83) 63.54%,
      #080808 100%
    );
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