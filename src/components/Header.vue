<template>
  <header class="pt-7 pb-1 h-20">
    <div class="flex-center-between">
      <div class="flex-center gap-5">
        <span>
          <img src="@/static/images/logo.png" alt="logo" />
        </span>
        <div class="w-px h-12 bg-[#ffffff14]"></div>
        <span class="avatar">
          <img class="avatar__img" src="@/static/images/user.jpeg" alt="" />
        </span>
      </div>

      <div class="flex-center gap-6">
        <span class="search">
          <icon-base class="search__icon" name="serach" />
          <input class="search__input" type="text" placeholder="Поиск" />
        </span>
        <span class="avatar">
          <img class="avatar__img" src="@/static/images/user.jpeg" alt="" />
        </span>
      </div>
    </div>
  </header>
</template>

<script>
import IconBase from "@/components/common/IconBase.vue";
export default {
  components: {
    IconBase,
  },
};
</script>

<style lang="scss" scoped>
.avatar {
  display: inline-block;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  overflow: hidden;
  background-color: #eee;
  &__img {
    width: 100%;
    object-fit: cover;
  }
}

.search {
  position: relative;
  padding: 4px 8px 4px 36px;
  display: inline-block;
  width: 103px;
  // border: 1px solid #eee;
  border-radius: 6px;
  &__icon {
    position: absolute;
    top: 50%;
    left: 8px;
    transform: translateY(-50%);
  }
  &__input {
    width: 100%;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: rgba(255, 255, 255, 0.9);
    background-color: transparent;
    &:focus-visible {
      outline: none;
    }

    &::placeholder {
      font-weight: 500;
      font-size: 16px;
      line-height: 20px;
      color: rgba(255, 255, 255, 0.9);
    }
  }
}
</style>fff