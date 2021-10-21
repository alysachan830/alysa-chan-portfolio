<template>
  <div>
    <div class="banner-bg-wrap position-relative vw-100 mb-20">
      <div
        class="
          banner-bg
          position-absolute
          vw-100
          d-flex
          justify-content-center
          align-items-center
        "
      >
        <div class="text-center">
          <!-- <img class="banner-icon" src="@/assets/images/dev_icon.png" alt="" /> -->
          <p class="banner-icon fw-bold text-primary">
            &lt; <span class="align-middle">/</span> &gt;
          </p>
          <h2 class="text-uppercase fw-bold banner-bg__title">alysa chan</h2>
          <h3 class="text-info font-l mb-16">
            A front-end developer with design sense.
          </h3>
          <ul class="d-flex justify-content-center mb-18">
            <li class="me-10">
              <a href="#">
                <img
                  class="social-media-icon"
                  src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                  alt=""
                />
              </a>
            </li>
            <li>
              <a href="#">
                <img
                  class="social-media-icon"
                  src="images/317712_code repository_github_repository_resource_icon.svg"
                  alt=""
                />
              </a>
            </li>
          </ul>
          <a
            href="#works"
            class="px-14 py-4 btn btn-primary btn-lg text-uppercase"
            >All works</a
          >
        </div>
      </div>
    </div>
    <div>
      <section class="mb-20 container">
        <h2 id="works" class="fw-bold font-2xl mb-20 text-uppercase">Works</h2>
        <ul>
          <li
            v-for="work in works"
            :key="work.title"
            class="row justify-content-between mb-20"
          >
            <a href="#" class="col-md-7 mb-5 mb-md-0">
              <div class="img--hover--zoom">
                <img :src="work.img" alt="" />
              </div>
            </a>
            <a href="#" class="col-md-4">
              <h2 class="mb-5">{{ work.title }}</h2>
              <ul class="d-flex text-info mb-12">
                <li v-for="skill in work.skills" :key="skill" class="me-5">
                  {{ skill }}
                </li>
              </ul>
              <a v-if="work.sourceCode" :href="work.sourceCode">
                <img
                  class="social-media-icon"
                  src="images/317712_code repository_github_repository_resource_icon.svg"
                  alt="github"
                />
              </a>
            </a>
          </li>
        </ul>
      </section>
      <section class="info-bg">
        <div class="container py-20">
          <h2 class="fw-bold font-2xl mb-20 text-uppercase">Articles</h2>
          <ul>
            <li
              v-for="article in articles"
              :key="article.title"
              class="article-card p-16 p-md-0 mb-6"
            >
              <a
                :href="article.url"
                class="row justify-content-center py-md-18 py-0"
                target="_blank"
              >
                <div class="col-md-5 mb-16 mb-md-0">
                  <a href="#" class="mb-10">
                    <img
                      class="article-card__icon mx-auto mx-md-0"
                      :src="article.img"
                      alt=""
                    />
                  </a>
                  <div>
                    <p class="mb-2 text-info fw-bold">
                      {{ article.subTitle }}
                    </p>
                    <h3 class="mb-10 fw-bold">{{ article.title }}</h3>
                    <p class="text-info">{{ article.post }} articles</p>
                  </div>
                </div>
                <div class="col-md-5">
                  <p v-if="article.prize" class="text-primary font-s mb-6">
                    <span class="material-icons align-top"> emoji_events </span>
                    {{ article.prize }}
                  </p>
                  <p class="mb-16 font-s font-md-base">
                    {{ article.description }}
                  </p>
                  <span class="text-primary text-end d-block article-card__link"
                    >Read more
                    <span class="material-icons align-middle">
                      chevron_right
                    </span>
                  </span>
                </div>
              </a>
            </li>
          </ul>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          title: 'Marugo Class Web App & LINE Chatbot',
          img: 'images/marugo-mock-up.jpg',
          skills: ['Vue.js', 'Express.js', 'Bootstrap 5'],
        },
        {
          title: 'Flash Ticketing',
          img: 'images/marugo-mock-up.jpg',
          skills: ['Nuxt.js', 'Express.js', 'Bootstrap 5'],
          sourceCode: 'https://github.com/alysachan830/flash-ticketing',
        },
        {
          title: 'Deluxury Website Design',
          img: 'images/deluxury_cover.jpg',
          skills: ['UI/UX design'],
        },
      ],
      articles: [
        {
          img: 'images/282802_javascript_js_icon.svg',
          title: 'JavaScript 基本功修煉',
          subTitle: '12th iThome Ironman 第 12 屆 IT 邦鐵人賽',
          prize: `Judge's selection 評選佳作`,
          post: 31,
          description: `iThome Ironman is a competition of writing technical articles for 30 days. In September 2020 , I joined the competition which had around 500 participants and shared my knowledge about JavaScript for 30 days.  My series of articles was selected as one of the Judge's Selections (評選佳作) at the end of the competition.`,
          url: 'https://ithelp.ithome.com.tw/users/20128534/ironman/3460',
        },
        {
          img: 'images/4691448_dot_js_vue_icon.svg',
          title: '不只懂 Vue 語法：Vue.js 觀念篇',
          subTitle: '13th iThome Ironman 第 13 屆 IT 邦鐵人賽',
          post: 31,
          description: `I participated in 13th iThome Ironman competition again in September 2021, for writing technical articles about the concepts of Vue.js for 30 days. To strengthen my skills with Vue.js, I tried to have an in-depth study in the syntax and core concepts in Vue.js through sharing my articles online.`,
          url: 'https://ithelp.ithome.com.tw/users/20128534/ironman/4377',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.banner-icon {
  font-size: 50px;

  span {
    font-size: 64px;
  }
}

.banner-bg {
  &-wrap {
    height: 50vh;
  }

  background: linear-gradient(#ffffff, #f0f1ff, #c9cdff);
  top: 0;
  left: 0;
  height: calc(50vh - 64px);

  &__title {
    font-size: 84px;
    letter-spacing: 4px;
  }
}

.info-bg {
  background: #fcfcfc;
}

.social-media-icon {
  width: 30px;
  height: 30px;
}

.article-card {
  transition: box-shadow 0.2s;

  &__icon {
    width: 100px;
    height: 100px;
  }

  &:hover {
    box-shadow: 2px 4px 10px #f4f4f4;

    .article-card__link {
      transform: translateX(8px);
    }
  }
}

.article-card__link {
  transition: transform 0.4s;
}
</style>
