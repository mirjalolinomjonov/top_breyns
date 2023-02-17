<template>
  <main>
    <div class="container-grid">
      <Header class="col-start-2 col-span-10 xl:hidden" />

      <main-video class="xl:block hidden col-start-1 col-span-12" />
      <!-- MAIN CONTENT -->
      <div
        class="col-start-2 col-span-7 xl:col-start-2 xl:col-span-10 relative"
      >
        <!-- VIDEO -->
        <main-video class="xl:hidden" />

        <!-- show content max-width: 1280px -->
        <div class="xl:block hidden">
          <div class="devider mt-5 mb-[4px]"></div>
          <Tabs @handle="currentTab = $event" />
          <div v-if="currentTab === 4">
            <lesson-list :lesson="lesson" />
          </div>
        </div>

        <div class="devider mt-8 mb-4 xl:mt-3"></div>

        <!-- ARTICLE -->
        <div>
          <Title title="Читайте также" class="mb-5" />
          <div class="grid grid-cols-7 ls:grid-cols-2 gap-8">
            <Article
              class="col-span-3 ls:col-span-1 md:col-span-2"
              v-for="item in 2"
              :key="item"
            />
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
            class="w-[404px] ls:max-w-[300px] mt-2 mb-6"
            color="#ffffff80"
            paragraph="TopBreyns снимает курсы от ещё многих профессионалов, которые вам будут интересны"
          />
          <div
            class="
              flex-center
              xs:flex-col
              gap-8
              max-w-[1050px]
              overflow-hidden
              sm:border sm:border-[#ffffff0a]
              rounded-[10px]
              corusel
              xs:before:hidden
            "
          >
            <!-- ls:h-[515px] -->
            <teacher-info
              v-for="(item, index) in techerInfo"
              :key="index"
              v-bind="{
                img: index,
                title: item?.title,
                subtitle: item?.subtitle,
                description: item?.description,
              }"
            />
          </div>
        </div>

        <!-- show mobile device -->
        <div class="linear-gradient hidden xs:block">
          <button
            class="
              more-teach-info
              hidden
              sm:flex-center-center
              transition
              hover:bg-[#ffffff33]
            "
          >
            <icon-base name="arrowe_down" />
          </button>
        </div>
      </div>

      <!-- ASIDE CONTENT-->
      <div class="col-start-9 col-span-3 xl:hidden">
        <!-- lesson list -->
        <lesson-list :lesson="lesson" />
      </div>
    </div>

    <!-- FOOTER CONTENT -->
    <div class="bg-[#141414] mt-20">
      <div class="container-grid">
        <Footer class="col-start-3 col-span-8 md:col-start-1 md:col-span-12" />
      </div>
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
import Footer from "../components/Footer.vue";
import TeacherInfo from "../components/TeacherInfo.vue";
import Tabs from "../components/Tabs.vue";
import IconBase from "../components/common/IconBase.vue";
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
    TeacherInfo,
    Tabs,
    IconBase,
  },
  data() {
    return {
      currentTab: 0,
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

      techerInfo: [
        {
          img: "",
          title: "Rober Reffikin",
          subtitle: "32 урока  ·  4 часа  ·  Программа",
          description:
            "Как генеральный директор и основатель Compass Роберт Реффкин использовал.",
        },
        // {
        //   img: "",
        //   title: "Daniel Pink",
        //   subtitle: "Скоро...",
        //   description:
        //     "Как генеральный директор и основатель Compass Роберт Реффкин использовал.",
        // },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.corusel {
  position: relative;
  &::before {
    content: "";
    position: absolute;
    right: 0;
    top: 0;
    width: 224px;
    height: 100%;
    background: linear-gradient(270deg, #080808 0%, rgba(8, 8, 8, 0) 35.94%, rgba(8, 8, 8, 0) 100%);
  }
}
.linear-gradient {
  width: 100%;
  height: 103px;
  position: absolute;
  bottom: 0;
  background: linear-gradient(
    180deg,
    rgba(8, 8, 8, 0) 0%,
    rgba(8, 8, 8, 0.83) 63.54%,
    #080808 100%
  );
  // background-color: #fff;
  .more-teach-info {
    width: 56px;
    height: 56px;
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(4px);
    border-radius: 50%;
    position: absolute;
    left: 50%;
    bottom: 0;
    transform: translate(-50%, -50%);
  }
}
</style>