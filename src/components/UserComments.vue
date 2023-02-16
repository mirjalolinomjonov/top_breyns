<template>
  <div class="user">
    <div class="user__img">
      <img src="@/static/images/user.jpeg" alt="" />
    </div>
    <div>
      <h3 class="user__name">{{ userName }}</h3>
      <span class="user__comment-time">{{ commentTime }}</span>
      <p class="user__message">{{ comment }}</p>

      <!-- replace comment -->
      <template v-for="(item, index) in replace">
        <div class="user mt-8" v-if="item?.isThere" :key="index">
          <div class="user__img">
            <img src="@/static/images/user.jpeg" alt="" />
          </div>
          <div>
            <h3 class="user__name" :class="{ admin: item?.isAdmin }">
              {{ item.userName }}
            </h3>
            <span class="user__comment-time">{{ item?.commentTime }}</span>
            <p class="user__message">{{ item?.comment }}</p>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    userName: {
      type: String,
      default: () => "",
    },
    commentTime: {
      type: String,
      default: () => "",
    },
    comment: {
      type: String,
      default: () => "",
    },
    replace: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.user {
  display: flex;
  gap: 20px;
  // user__img
  &__img {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    overflow: hidden;
    flex-shrink: 0;
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  // user__name
  &__name {
    display: inline-block;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: -0.4px;
    color: #ffffff;
    &.admin {
      background: rgba(255, 255, 255, 0.16);
      border: 1px solid rgba(255, 255, 255, 0.04);
      border-radius: 6px;
      padding: 0 6px;
    }
  }
  // user__comment-time
  &__comment-time {
    display: block;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: -0.4px;
    margin-bottom: 8px;
    color: rgba(255, 255, 255, 0.5);
  }
  // user__message
  &__message {
    font-weight: 500;
    font-size: 16px;
    line-height: 22px;
    color: rgba(255, 255, 255, 0.9);
  }
}
</style>