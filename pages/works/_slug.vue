<template>
  <div class="mt-20 mt-lg-21">
    <div class="container mb-16">
      <div class="row justify-content-between flex-column-reverse flex-md-row">
        <div class="col-md-8">
          <span class="font-m"> {{ page.year }} </span>
          <h2 class="font-md-2xl font-xl">{{ page.title }}</h2>
        </div>
        <div class="col-md-4">
          <a
            class="back-to-works-btn text-info text-end mb-8 mb-md-0 font-s"
            href="/#works"
            >Back to works
            <span class="material-icons align-middle font-s">
              chevron_right
            </span>
          </a>
        </div>
      </div>
    </div>

    <div
      class="cover-img mb-md-21 mb-20"
      :style="`background-image: url(${page.coverImg})`"
    ></div>
    <div class="markdown-body">
      <div class="container mb-md-21 mb-20">
        <div class="row justify-content-between mb-20 mb-md-0">
          <div class="col-md-7 mb-18 mb-md-0">
            <h2 class="fw-bold font-l mb-8">
              {{ page.title }}
            </h2>
            <p>{{ page.description }}</p>
          </div>
          <ul class="col-md-4">
            <li class="mb-10">
              <p class="fw-bold mb-3">URL</p>
              <a
                v-if="/^https/.test(page.url)"
                :href="page.url"
                class="hover--primary"
                target="_blank"
              >
                {{ page.url }}
              </a>
              <span v-else> {{ page.url }} </span>
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
            <li class="mb-10">
              <p class="fw-bold mb-3">Technologies</p>
              {{ page.technologies }}
            </li>
            <li>
              <p class="fw-bold mb-3">Source code</p>
              <a
                v-if="page.sourceCode"
                :href="page.sourceCode"
                class="me-8"
                target="_blank"
              >
                <img
                  class="icon"
                  src="/images/317712_code repository_github_repository_resource_icon.svg"
                  alt="github"
                />
              </a>
              <span v-else> - </span>
            </li>
          </ul>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <div class="markdown-content work-content mb-18">
            <nuxt-content :document="page" />
          </div>
        </div>
      </div>
    </div>
    <div class="container mb-18">
      <a
        class="back-to-works-btn text-info mb-8 mb-md-0 text-end"
        href="/#works"
        >Back to works
        <span class="material-icons align-middle"> chevron_right </span>
      </a>
    </div>
  </div>
</template>

<script>
import ImageWrap from '../../components/ImageWrap.vue'

export default {
  components: {
    // eslint-disable-next-line vue/no-unused-components
    ImageWrap,
  },
  async asyncData({ $content, params, error }) {
    const slug = params.slug || 'index'
    const page = await $content(`works/${slug}`)
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
@import '@/assets/stylesheets/markdown-content/markdown-content';

.cover-img {
  width: 100%;
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;

  height: 240px;

  @include media-breakpoint-up(md) {
    height: 532px;
  }

  @include media-breakpoint-up(lg) {
    height: 665px;
  }

  @include media-breakpoint-up(xxl) {
    height: 1280px;
  }
}

.icon {
  width: 24px;
}

.role ul {
  list-style-type: disc;
  list-style-position: inside;
}

.work-content {
  p {
    @include media-breakpoint-up(md) {
      width: 70%;
    }
  }
}

.back-to-works-btn {
  transition: transform 0.4s;
  &:hover {
    transform: translateX(8px);
  }
}
</style>
