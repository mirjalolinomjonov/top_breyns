<template>
  <article
    class="
      py-[10px]
      pr-[10px]
      pl-6
      bg-[#ffffff0a]
      rounded-[10px]
      border border-[#ffffff0a]
      flex-center-between
    "
  >
    <div>
      <h4
        class="
          mb-2
          text-[#ffffff66] text-[15px]
          leading-[20px]
          font-medium
          flex-center
          gap-1
        "
      >
        <icon-base name="article_burger" />
        <span> Статья </span>
      </h4>
      <p class="text-[#ffffffe6] text-base leading-[22px] font-medium">
        Прогнозы трендов продаж на ближайшие пять лет
      </p>
    </div>

    <figure class="inline-block shrink-0 w-[118px] h-[94px] overflow-hidden rounded-md border border-[#ffffff14]">
      <img class="w-full h-full object-cover" src="@/static/images/article.png" alt="">
    </figure>
  </article>
</template>

<script>
import IconBase from "./common/IconBase.vue";
export default {
  components: {
    IconBase,
  },
};
</script>

<style lang="scss" scoped>
</style>