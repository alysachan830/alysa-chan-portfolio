<template>
  <div>
    <div class="banner-bg-wrap position-relative vw-100 mb-20">
      <div
        class="
          banner-bg
          h-100
          position-absolute
          vw-100
          d-flex
          justify-content-center
          align-items-center
        "
      >
        <div class="text-center container">
          <p class="banner-icon fw-bold text-primary">
            &lt; <span class="align-middle">/</span> &gt;
          </p>
          <h2 class="text-uppercase fw-bold banner-bg__title">alysa chan</h2>
          <h3 class="text-info font-md-l font-m mb-md-16 mb-10">
            A front-end developer with design sense.
          </h3>
          <ul class="d-flex justify-content-center mb-md-18 mb-12">
            <li class="me-10">
              <a href="#" target="_blank">
                <img
                  class="icon--l"
                  src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                  alt="linkedIn"
                />
              </a>
            </li>
            <li>
              <a href="https://github.com/alysachan830" target="_blank">
                <img
                  class="icon--l"
                  src="images/317712_code repository_github_repository_resource_icon.svg"
                  alt="github"
                />
              </a>
            </li>
          </ul>
          <a
            href="#works"
            class="px-md-14 py-md-4 btn btn-primary btn-md-lg text-uppercase"
            >All works</a
          >
        </div>
      </div>
    </div>
    <div>
      <section class="mb-20 container">
        <h2
          id="works"
          class="fw-bold font-md-2xl font-xl mb-18 mb-md-20 text-uppercase"
        >
          Works
        </h2>
        <ul>
          <li
            v-for="work in workIntros"
            :key="work.title"
            class="row justify-content-between mb-20"
          >
            <NuxtLink :to="`/works/${work.path}`" class="col-md-7 mb-5 mb-md-0">
              <div class="img--hover--zoom">
                <img :src="work.imageUrl" :alt="work.title" />
              </div>
            </NuxtLink>
            <div class="work col-md-4">
              <NuxtLink :to="`/works/${work.path}`" class="mb-14">
                <span class="mb-3 d-block"> {{ work.year }} </span>
                <span class="mb-1 d-block font-l fw-medium">{{
                  work.title
                }}</span>
                <ul class="d-flex flex-wrap text-info">
                  <li
                    v-for="skill in work.technologies"
                    :key="skill"
                    class="me-5"
                  >
                    {{ skill }}
                  </li>
                </ul>
              </NuxtLink>
              <NuxtLink
                :to="`/works/${work.path}`"
                class="work__read-more mb-lg-12 mb-8 font-s"
              >
                Read more
                <span class="material-icons align-middle"> chevron_right </span>
              </NuxtLink>
              <div class="d-flex">
                <a
                  v-if="work.sourceCode"
                  :href="work.sourceCode"
                  class="me-8"
                  target="_blank"
                >
                  <img
                    class="icon"
                    src="images/317712_code repository_github_repository_resource_icon.svg"
                    alt="github"
                  />
                </a>
                <a v-if="work.url" :href="work.url" target="_blank">
                  <img
                    class="icon"
                    src="images/2561457_link_icon.svg"
                    alt="link"
                  />
                </a>
              </div>
            </div>
          </li>
        </ul>
      </section>
      <section id="articles" class="info-bg">
        <div class="container py-20">
          <h2 class="fw-bold font-md-2xl font-xl mb-18 mb-md-20 text-uppercase">
            Articles
          </h2>
          <ul>
            <li
              v-for="article in articleIntros"
              :key="article.title"
              class="article-card p-16 p-md-0 mb-6"
              @click="toArticle(article.url)"
            >
              <div
                class="article-link row justify-content-center py-md-18 py-0"
              >
                <div class="col-md-5 mb-16 mb-md-0">
                  <a href="#" class="mb-10">
                    <img
                      class="article-card__icon mx-auto mx-md-0"
                      :src="article.img"
                      alt=""
                    />
                  </a>
                  <span>
                    <p class="mb-2 text-info fw-bold">
                      {{ article.subTitle }}
                    </p>
                    <h3 class="mb-10 fw-bold">{{ article.title }}</h3>
                    <p class="text-info">{{ article.post }} articles</p>
                  </span>
                </div>
                <div class="col-md-5">
                  <p v-if="article.prize" class="text-primary font-s mb-6">
                    <span class="material-icons align-top"> emoji_events </span>
                    {{ article.prize }}
                  </p>
                  <p class="mb-16 font-s font-md-base">
                    {{ article.description }}
                  </p>
                  <span class="text-end d-block article-card__link"
                    >Read more
                    <span class="material-icons align-middle">
                      chevron_right
                    </span>
                  </span>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const workIntros = await $content('workIntros')
      .fetch()
      .then((res) => res[0].workIntros)
      .catch(() => {
        error({ statusCode: 404, message: 'Page not found' })
      })

    const articleIntros = await $content('articleIntros')
      .fetch()
      .then((res) => res[0].articleIntros)
      .catch(() => {
        error({ statusCode: 404, message: 'Page not found' })
      })
    return {
      workIntros,
      articleIntros,
    }
  },
  mounted() {
    if (this.$nuxt.$route.hash !== '') {
      const el = document.querySelector(this.$nuxt.$route.hash)
      el.scrollIntoView({ behavior: 'smooth' })
    }
  },
  methods: {
    toArticle(url) {
      window.open(url)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/stylesheets/all';

.banner-icon {
  font-size: 40px;
  @include media-breakpoint-up(md) {
    font-size: 50px;
  }

  span {
    font-size: 54px;
    @include media-breakpoint-up(md) {
      font-size: 64px;
    }
  }
}

.banner-bg {
  &-wrap {
    // Nav bar is 64px height
    margin-top: 64px;
    height: calc(100vh - 64px);
    @include media-breakpoint-up(md) {
      height: 60vh;
    }
  }

  background: linear-gradient(#ffffff, #f0f1ff, #c9cdff);
  top: 0;
  left: 0;

  &__title {
    @include media-breakpoint-up(md) {
      font-size: 84px;
      letter-spacing: 4px;
    }

    font-size: 34px;
    letter-spacing: 2px;
  }
}

.info-bg {
  background: #fcfcfc;
}

.icon {
  width: 22px;
  height: 22px;

  &--l {
    width: 30px;
    height: 30px;
  }
}

.work {
  &__read-more {
    transition: transform 0.4s;
  }
  &:hover {
    .work__read-more {
      transform: translateX(8px);
    }
  }
}

.article-card {
  transition: box-shadow 0.2s;
  cursor: pointer;

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
