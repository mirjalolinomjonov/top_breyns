<template>
  <main class="container-grid">
    <Header class="col-start-2 col-span-10" />
    <!-- main video -->
    <main-video class="col-start-2 col-span-7" />
    <!-- lesson list -->
    <lesson-list class="col-start-9 col-span-3" :lesson="lesson" />
  </main>
</template>

<script>
import Header from "@/components/Header.vue";
import LessonList from "../components/LessonList.vue";
import MainVideo from "../components/MainVideo.vue";
export default {
  components: {
    Header,
    MainVideo,
    LessonList,
  },
  data() {
    return {
      lesson: [
        {
          title: "Знакомство",
          child: [
            {
              name: "Встречайте, Даниэль Пинк",
              time: 8,
              description: "",
            },
            {
              name: "Тренды Продаж",
              time: 12,
              description:
                "Дэн представляет себя, класс, то, что вы узнаете, и объясняет, почему для всех.",
              currentLesson: true,
            },
            {
              name: "Поиск точек соприкосновения",
              time: 20,
              description: "",
            },
            {
              name: "Служить своей аудитории",
              time: 18,
              description: "",
            },
          ],
        },
        {
          title: "Знакомство",
          child: [
            {
              name: "Встречайте, Даниэль Пинк",
              time: 8,
              description: "",
            },
            {
              name: "Тренды Продаж",
              time: 12,
              description:
                "Дэн представляет себя, класс, то, что вы узнаете, и объясняет, почему для всех.",
            },
            {
              name: "Поиск точек соприкосновения",
              time: 20,
              description: "",
            },
            {
              name: "Служить своей аудитории",
              time: 18,
              description: "",
            },
          ],
        },
        {
          title: "Знакомство",
          child: [
            {
              name: "Встречайте, Даниэль Пинк",
              time: 8,
              description: "",
            },
            {
              name: "Тренды Продаж",
              time: 12,
              description:
                "Дэн представляет себя, класс, то, что вы узнаете, и объясняет, почему для всех.",
            },
            {
              name: "Поиск точек соприкосновения",
              time: 20,
              description: "",
            },
            {
              name: "Служить своей аудитории",
              time: 18,
              description: "",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>