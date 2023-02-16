<template>
  <div class="msg">
    <span class="msg__avatar">
      <img
        class="w-full h-full object-cover"
        src="@/static/images/user.jpeg"
        alt=""
      />
    </span>
    <input class="msg__input" type="text" placeholder="Оставить отзыв..." />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.msg {
  display: flex;
  align-items: center;
  gap: 20px;
  // msg__avatar
  &__avatar {
    width: 44px;
    height: 44px;
    border: 1px solid rgba(255, 255, 255, 0.08);
    overflow: hidden;
    border-radius: 50%;
    flex-shrink: 0;
  }
  // msg__input
  &__input {
    display: block;
    width: 100%;
    padding: 12px 0;
    font-weight: 500;
    font-size: 17px;
    line-height: 24px;
    letter-spacing: -0.4px;
    color: #fff;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    background-color: transparent;
    transition: all .2s ease-in-out;
    &:focus-visible{
      outline: none;
      border-color: #fff;
    }
    &::placeholder{
      color: rgba(255, 255, 255, 0.4);
    }
  }
}
</style>