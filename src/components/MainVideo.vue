<template>
  <section>
    <!-- video wrapper -->
    <div
      class="
        border border-solid border-[#ffffff14]
        rounded-[10px]
        overflow-hidden
        h-[603px]
        md:h-[400px]
        sm:h-[320px]
        xs:h-[180px]
        md:rounded-none
      "
    >
      <iframe
        class="w-full h-full"
        src="https://www.youtube.com/embed/stGfw_T821g"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
    </div>

    <!-- video description -->
    <div class="xl:grid xl:grid-cols-12">
      <div class="xl:col-start-2 xl:col-span-10">
        <!-- title -->
        <span
          class="
            text-[#F8A404] text-[15px]
            leading-[20px]
            font-medium
            tracking-[0.1px]
            block
            mt-8
            mb-1
          "
        >
          Знакомство
        </span>
        <!-- current video's description -->
        <div class="flex-between">
          <div>
            <h2 class="text-white text-[24px] leading-[32px] font-bold mb-3">
              2. Тренды Продаж
            </h2>
            <p class="text-[#ffffff80] text-base leading-[22px] w-[440px] ls:max-w-[320px] xs:w-[270px] xl:max-w-[800px]">
              Дэн представляет себя, класс, то, что вы узнаете, и объясняет,
              почему для всех.
            </p>
          </div>
  
          <!-- bookmark and chat buttons -->
          <div class="flex-center self-start gap-4 xl:hidden">
            <button
              v-for="item in 2"
              :key="item"
              class="
                flex-center-center
                w-12
                h-12
                rounded-full
                bg-[#ffffff1a]
                backdrop-blur-sm
                border border-[#ffffff0a]
                transition
                hover:bg-[#ffffff33]
                cursor-pointer
              "
            >
              <icon-base :name="item == 1 ? 'bookmark_added' : 'chat'" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import IconBase from "./common/IconBase.vue";
export default {
  components: { IconBase },
};
</script>

<style lang="scss" scoped>
</style>