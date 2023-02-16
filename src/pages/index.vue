<template>
  <main class="container-grid">
    <Header class="col-start-2 col-span-10" />
    <!-- MAIN CONTENT -->
    <div class="col-start-2 col-span-7">
      <!-- VIDEO -->
      <main-video />
      <div class="devider mt-8 mb-4"></div>

      <!-- ARTICLE -->
      <div>
        <Title title="Читайте также" class="mb-5" />
        <div class="grid grid-cols-7 gap-8">
          <Article class="col-span-3" v-for="item in 2" :key="item" />
        </div>
      </div>

      <div class="devider mt-9 mb-[15px]"></div>

      <!-- COMMENTS -->
      <div>
        <Title class="mb-[26px]" title="32 Комментария" />
        <send-message class="mb-10" />
        <div class="flex flex-col gap-8">
          <user-comments
            v-for="(item, index) in comments"
            :key="index"
            v-bind="{
              userName: item?.userName,
              commentTime: item?.commentTime,
              comment: item?.comment,
              replace: item?.replace,
            }"
          />

          <button
            class="
              text-[#ffffffe6] text-lg
              leading-[24px]
              font-medium
              self-start
              py-3
              px-5
              transition
              hover:text-[#fff]
            "
          >
            Показать ещё
          </button>
        </div>
      </div>

      <div class="devider mt-9 mb-[15px]"></div>

      <!-- COURSES -->
      <div>
        <Title title="Курсы" />
        <Paragraph
          class="w-[404px] mt-2 mb-6"
          color="#ffffff80"
          paragraph="TopBreyns снимает курсы от ещё многих профессионалов, которые вам будут интересны"
        />
      </div>
    </div>

    <!-- ASIDE CONTENT-->
    <div class="col-start-9 col-span-3">
      <!-- lesson list -->
      <lesson-list :lesson="lesson" />
    </div>

    <!-- FOOTER CONTENT -->
    <div  class="col-span-12 grid grid-cols-12 bg-[#141414]">
      <Footer  class="col-start-2 col-span-10"/>
    </div>
  </main>
</template>

<script>
import Header from "@/components/Header.vue";
import LessonList from "../components/LessonList.vue";
import MainVideo from "../components/MainVideo.vue";
import Article from "../components/Article.vue";
import Title from "../components/Title.vue";
import SendMessage from "../components/SendMessage.vue";
import UserComments from "../components/UserComments.vue";
import Paragraph from "../components/Paragraph.vue";
import Footer from '../components/Footer.vue';
export default {
  components: {
    Header,
    MainVideo,
    LessonList,
    Article,
    Title,
    SendMessage,
    UserComments,
    Paragraph,
    Footer,
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

      comments: [
        {
          userImg: "",
          userName: "KKomol",
          commentTime: "2 дня назад",
          comment:
            "Нет ребят я конечно все понимаю таких фильмов с похожим сюжетом пруд пруди, но думаю именно этот стоит посмотреть :)",
          replace: [
            {
              isAdmin: true,
              isThere: true,
              userImg: "",
              userName: "TopBreyns - Поддержка",
              commentTime: "1 день назад",
              comment: "Нет ребят я конечно все понимаю таких фильмов",
            },
            {
              isAdmin: false,
              isThere: true,
              userImg: "",
              userName: "Jon Doe",
              commentTime: "7 день назад",
              comment: "Нет ребят я конечно все понимаю таких фильмов",
            },
          ],
        },
        {
          userImg: "",
          userName: "Amaliya Cat",
          commentTime: "6 дня назад",
          comment:
            "Нет ребят я конечно все понимаю таких фильмов с похожим сюжетом пруд пруди, но думаю именно этот стоит посмотреть :)",
          replace: [
            {
              isAdmin: false,
              isThere: false,
              userImg: "",
              userName: "",
              commentTime: "",
              comment: "",
            },
          ],
        },
        {
          userImg: "",
          userName: "Annamana",
          commentTime: "8 дня назад",
          comment:
            "Нет ребят я конечно все понимаю таких фильмов с похожим сюжетом пруд пруди, но думаю именно этот стоит посмотреть :)",
          replace: [
            {
              isAdmin: false,
              isThere: true,
              userImg: "",
              userName: "Abdullokh",
              commentTime: "4 день назад",
              comment: "Нет ребят я конечно все понимаю таких фильмов",
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