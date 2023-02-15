<template>
  <section>
    <!-- video wrapper -->
    <div
      class="
        border border-silid border-[#ffffff14]
        rounded-[10px]
        overflow-hidden
        h-[603px]
      "
    >
      <iframe
        class="w-full h-full"
        src="https://www.youtube.com/embed/sb6WlQiaJeM"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
    </div>

    <!-- video description -->
    <div>
      <span>Знакомство</span>
      <div class="flex-between">
        <div>
          <h2>2. Тренды Продаж</h2>
          <p>
            Дэн представляет себя, класс, то, что вы узнаете, и объясняет,
            почему для всех.
          </p>
        </div>
        <div>
          <button v-for="item in 2" :key="item">
            <icon-base :name="item == 1 ? 'bookmark_added' : 'chat'" />
          </button>
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