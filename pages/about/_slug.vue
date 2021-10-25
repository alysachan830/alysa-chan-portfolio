<template>
  <div class="mt-20 mt-lg-21 mb-21 markdown-body">
    <div class="container">
      <h2 class="fw-bold font-2xl mb-20 text-uppercase">About me</h2>
      <div
        class="row flex-column-reverse flex-lg-row justify-content-lg-between"
      >
        <div class="markdown-content col-lg-7">
          <nuxt-content :document="page" />
        </div>
        <div
          class="
            mb-16 mb-lg-0
            col-lg-4
            d-flex
            justify-content-center justify-content-lg-end
          "
        >
          <img
            class="profile-img"
            src="/images/profile_pic.jpg"
            alt="profile image"
          />
        </div>
      </div>
      <div class="contact">
        <h2>Contact</h2>
        <ul>
          <li class="mb-8">
            <a
              href="mailto:alysachansl@gmail.com"
              class="d-flex align-items-center hover--primary"
            >
              <img class="me-8" src="images/email_black_24dp.svg" alt="email" />
              <span class="font-m">alysachansl@gmail.com</span>
            </a>
          </li>
          <li class="mb-8">
            <a
              href="#"
              class="d-flex align-items-center hover--primary"
              target="_blank"
            >
              <img
                class="me-8"
                src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                alt="linkedIn"
              />
              <span class="font-m">Alysa Chan</span>
            </a>
          </li>
          <li>
            <a
              href="https://github.com/alysachan830"
              class="d-flex align-items-center hover--primary"
              target="_blank"
            >
              <img
                class="me-8"
                src="images/317712_code repository_github_repository_resource_icon.svg"
                alt="github"
              />
              <span class="font-m">alysachan830</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const page = await $content('about/about')
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
@import '@/assets/stylesheets/markdown-content/markdown-content.scss';
@import '@/assets/stylesheets/all.scss';

.profile-img {
  height: 240px;
  border-radius: 50%;
}

.about-list section {
  h2 {
    margin-bottom: 46px;
  }

  h3 {
    font-size: 18px;
    margin-bottom: 16px;
    font-weight: bold;
  }

  ul {
    list-style: none;
    margin-bottom: 42px;

    li:first-child {
      font-size: 14px;
      color: $info;
    }
  }
}

.contact {
  img {
    width: 34px;
  }
}
</style>
