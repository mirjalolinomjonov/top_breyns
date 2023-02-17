<template>
  <footer class="pt-20 pb-10 md:pb-0">
    <div class="flex justify-between flex-wrap md:flex-col md:items-center md:gap-12">
      <div class="md:text-center">
        <router-link to="/" class="inline-block">
          <img src="@/static/images/logo.png" alt="" />
        </router-link>
        <Paragraph
          class="w-[342px] ls:w-[300px] mt-3 mb-9"
          color="#ffffff66"
          paragraph="Онлайн курсы премиум качества от ведущих мастеров своей сферы"
        />
        <ul class="flex-center gap-4 md:justify-center">
          <li v-for="(item, index) in socials" :key="index">
            <a href="" target="_blank">
              <icon-base :name="item.icon" />
            </a>
          </li>
        </ul>
      </div>

      <nav v-for="(item, index) in navLinks" :key="index" class="nav">
        <ul class="nav-list md:text-center">
          <h3 class="nav-list__title">{{ item.title }}</h3>
          <li
            v-for="(link, index) in item.child"
            :key="index"
            class="nav-list__item"
          >
            <router-link :to="link.link" class="nav-list__item-anchor">
              {{ link.name }}
            </router-link>
          </li>
        </ul>
      </nav>

      <div class="md:text-center md:w-full">
        <h3 class="nav-list__title">Новости</h3>
        <p
          class="
            w-[323px]
            ls:w-[300px]
            text-[#ffffffe6] text-2xl
            leading-[32px]
            font-semibold
            md:inline-block
          "
        >
          Новости, анонсы и скидки в нашем телеграме
        </p>
        <a
          class="
            bg-[#38A5E0]
            rounded-[10px]
            py-3
            px-[25.5px]
            flex
            justify-center
            gap-2
            text-[18px] text-white
            font-medium
            mt-5
            transition
            hover:bg-[#38bdf8]
            md:w-full
            md:rounded-none
            text-center
          "
          href="#"
          target="_blank"
          ><icon-base name="telegram" /> Перейти</a
        >
      </div>
    </div>

    <div class="devider mt-14 mb-8 md:hidden"></div>
    
    <div class="flex-center gap-[40px] md:hidden">
      <router-link to="/">
        <img src="@/static/images/footer_logo.png" alt="" />
      </router-link>
      <p class="copyright-text">© 2021 TopBreyns</p>
      <p class="copyright-text flex-center gap-2">
        <icon-base name="lock" /> Secured with SSL
      </p>
    </div>
  </footer>
</template>

<script>
import IconBase from "./common/IconBase.vue";
import Paragraph from "./Paragraph.vue";
export default {
  components: { Paragraph, IconBase },
  data() {
    return {
      socials: [
        {
          icon: "facebook",
          link: "",
        },
        {
          icon: "instagram",
          link: "",
        },
        {
          icon: "telegram",
          link: "",
        },
        {
          icon: "youtube",
          link: "",
        },
      ],
      navLinks: [
        {
          title: "Все курсы",
          child: [
            {
              name: "Все курсы",
              link: "#",
            },
            {
              name: "Скоро",
              link: "#",
            },
            {
              name: "Поиск",
              link: "#",
            },
            {
              name: "Блог",
              link: "#",
            },
          ],
        },
        {
          title: "Формальности",
          child: [
            {
              name: "Условия использования",
              link: "#",
            },
            {
              name: "Политикой конф.",
              link: "#",
            },
            {
              name: "Контакты",
              link: "#",
            },
            {
              name: "Чат с поддержкой",
              link: "#",
            },
            {
              name: "Оплата",
              link: "#",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.nav {
  // nav-list
  &-list {
    // nav-list__title
    &__title {
      font-weight: 500;
      font-size: 16px;
      line-height: 22px;
      color: rgba(255, 255, 255, 0.4);
      margin-bottom: 24px;
    }
    &__item {
      // nav-list__item
      font-weight: 500;
      font-size: 16px;
      line-height: 22px;
      color: rgba(255, 255, 255, 0.9);
      &:not(:last-child) {
        margin-bottom: 20px;
      }
    }
  }
}
.copyright-text {
  font-weight: 500;
  font-size: 16px;
  line-height: 22px;
  color: rgba(255, 255, 255, 0.2);
}
</style>