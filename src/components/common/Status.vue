<template>
  <div class="status">
    <div class="relative z-[2] h-full w-full flex flex-col justify-between">
      <div>
        <figure
          v-if="!!img"
          class="
            w-12
            h-12
            rounded-full
            overflow-hidden
            border border-[#43ff6414]
          "
        >
          <img
            class="w-full object-cover"
            src="@/static/images/user2.png"
            alt=""
          />
        </figure>
        <h3
          v-else-if="countLesson || currentLesson || lessonForToday"
          class="
            text-[#ffffffe6] text-[32px]
            leading-[40px]
            font-semibold
            inline-flex
            items-center
          "
        >
          {{ currentLesson || lessonForToday
          }}<span v-if="countLesson" class="self-end text-[#71717a] text-2xl">
            /{{ countLesson }}
          </span>
        </h3>
      </div>
      <p class="status__title">{{ title }}</p>
    </div>
    <!-- progress -->
    <div
      v-if="currentLesson && countLesson"
      :data-size="currentLesson"
      ref="progress"
      class="progress"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    img: {
      type: String,
      requare: true,
    },
    currentLesson: {
      type: Number,
      default: () => null,
    },
    countLesson: {
      type: Number,
      default: () => null,
    },
    lessonForToday: {
      type: Number,
      default: () => null,
    },
    title: {
      type: String,
      default: () => "",
    },
  },
  mounted() {
    setTimeout(() => {
      const  size  = this.$refs.progress.dataset.size;
      this.$refs.progress.style.width = `${((size * 100) / this.countLesson).toFixed(1)}%`;
    }, 1000);
  },
};
</script>

<style lang="scss" scoped>
.status {
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(255, 255, 255, 0.04);
  border-radius: 10px;
  padding: 1rem;
  height: 114px;
  position: relative;
  .progress {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 0;
    transition: all .3s linear;
    background: linear-gradient(
      270deg,
      rgba(255, 255, 255, 0.04) 0%,
      rgba(255, 255, 255, 0) 100%
    );
  }

  // status__title
  &__title {
    font-weight: 500;
    font-size: 18px;
    line-height: 20px;
    color: rgba(255, 255, 255, 0.9);
  }
}
</style>