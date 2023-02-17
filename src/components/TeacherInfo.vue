<template>
  <div class="teach xs:flex-col h-full">
    <figure class="teach__img relative sm:w-max">
      <img
        v-if="img === 0"
        src="@/static/images/responsive_teach.png"
        alt=""
        class="hidden xs:inline-block"
      />
      <img
        v-if="img === 0"
        src="@/static/images/teach1.png"
        alt=""
        class="xs:hidden"
      />
      <img
        v-else-if="img === 1"
        src="@/static/images/teach2.png"
        alt=""
      />
      <button class="teach__player flex-center-center self-end xs:inline-flex hidden absolute right-14 bottom-0 translate-y-1/2">
        <icon-base name="player" />
      </button>
    </figure>
    <div class="teach-info flex flex-col">
      <h2 class="teach-info__title">{{ title }}</h2>
      <span class="teach-info__subtitle">{{ subtitle }}</span>
      <p class="teach-info__description">
        {{ description }}
      </p>
      <button class="teach__player flex-center-center self-end xs:hidden">
        <icon-base name="player" />
      </button>
    </div>
  </div>
</template>

<script>
import IconBase from "./common/IconBase.vue";
export default {
  components: { IconBase },
  props: {
    img: {
      type: Number,
    },
    title: {
      type: String,
      default: () => "",
    },
    subtitle: {
      type: String,
      default: () => "",
    },
    description: {
      type: String,
      default: () => "",
    },
  },
};
</script>

<style lang="scss" scoped>
.teach {
  display: flex;
  align-items: center;
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(255, 255, 255, 0.04);
  border-radius: 10px;
  overflow: hidden;
  width: 598px;
  flex-shrink: 0;

  // teach__img
  &__img {
    width: 234px;
    flex-shrink: 0;
    img {
      width: 100%;
    }
  }
  // teach-info
  &-info {
    padding: 48px 32px 20px;
    // teach-info__title
    &__title {
      font-family: "ITC Cheltenham";
      font-style: normal;
      font-weight: 700;
      font-size: 28px;
      line-height: 28px;
      color: rgba(255, 255, 255, 0.9);
    }
    // teach-info__subtitle
    &__subtitle {
      display: block;
      font-weight: 500;
      font-size: 13px;
      line-height: 16px;
      letter-spacing: 0.1px;
      color: rgba(255, 255, 255, 0.4);
      margin: 10px 0 14px;
    }
    // teach-info__description
    &__description {
      width: 248px;
      font-weight: 400;
      font-size: 15px;
      line-height: 20px;
      color: rgba(255, 255, 255, 0.9);
    }
  }

  // teach__player
  &__player {
    width: 40px;
    height: 40px;
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(4px);
    border-radius: 50%;
    transition: all 0.1s ease-in-out;
    &:hover {
      background: rgba(255, 255, 255, 0.2);
    }
  }
}
</style>