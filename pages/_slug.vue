<template>
  <!-- <div>
    <h1>{{ page.title }}</h1>
    <p>{{ page.description }}</p>
    <nuxt-content :document="page" />
  </div> -->
  <div class="mt-21">
    <div class="container mb-16">
      <div class="row justify-content-between flex-column-reverse flex-md-row">
        <div class="col-md-8">
          <span class="font-m"> {{ page.year }} </span>
          <h2 class="font-2xl">{{ page.title }}</h2>
        </div>
        <div class="col-md-4">
          <a class="text-info text-end mb-8 mb-md-0 font-s" href="/#works"
            >Back to works
            <span class="material-icons align-middle font-s">
              chevron_right
            </span>
          </a>
        </div>
      </div>
    </div>

    <div class="cover-img mb-21">
      <img :src="page.coverImg" :alt="page.title" />
    </div>
    <div class="body">
      <div class="container mb-21">
        <div class="row justify-content-between mb-20 mb-md-0">
          <div class="col-md-7">
            <h2 class="fw-bold font-l mb-8">
              {{ page.title }}
            </h2>
            <p>{{ page.description }}</p>
          </div>
          <ul class="col-md-3">
            <li class="mb-10">
              <p class="fw-bold mb-3">URL</p>
              {{ page.url }}
            </li>
            <li class="mb-10">
              <p class="fw-bold mb-3">My role</p>
              <ul>
                <li
                  v-for="role in page.role.split(',')"
                  :key="role"
                  class="role"
                >
                  {{ role }}
                </li>
              </ul>
            </li>
            <li>
              <p class="fw-bold mb-3">Technologies</p>
              {{ page.technologies }}
            </li>
          </ul>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <div class="content mb-18">
            <nuxt-content :document="page" />
          </div>
        </div>
      </div>
    </div>
    <div class="container mb-18">
      <a class="text-info mb-8 mb-md-0 font-m text-end" href="/#works"
        >Back to works
        <span class="material-icons align-middle"> chevron_right </span>
      </a>
    </div>
  </div>
</template>

<script>
import ImageWrap from '../components/ImageWrap.vue'

export default {
  components: {
    // eslint-disable-next-line vue/no-unused-components
    ImageWrap,
  },
  async asyncData({ $content, params, error }) {
    const slug = params.slug || 'index'
    const page = await $content(slug)
      .fetch()
      .catch(() => {
        error({ statusCode: 404, message: 'Page not found' })
      })

    return {
      page,
    }
  },
}
</script>

<style lang="scss">
@import '@/assets/stylesheets/all';

.cover-img {
  img {
    width: 100vw;
    height: 1280px;
  }
}

.role,
.content ul {
  list-style-type: disc;
  list-style-position: inside;
}

.body {
  line-height: 1.8;
  @include media-breakpoint-up(md) {
    font-size: 18px;
  }
  font-size: 16px;

  h2 {
    font-weight: bold;
    font-size: 24px;
    margin-bottom: 32px;
  }
}

.content {
  p {
    width: 70%;
  }

  p,
  ul {
    margin-bottom: 20px;
  }
}

.caption {
  color: $info;
  font-size: 14px;
  margin-bottom: 0.625rem;
}
</style>
