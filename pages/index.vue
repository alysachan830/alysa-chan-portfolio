<template>
  <div>
    <div class="position-relative vh-100 vw-100 mb-20">
      <div
        class="
          banner-bg
          position-absolute
          vw-100
          vh-100
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
          <h3 class="text-info mb-16">Front-end developer</h3>
          <ul class="d-flex justify-content-center mb-20">
            <li class="me-10">
              <a href="#">
                <img
                  class="social-media-icon"
                  src="@/assets/images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                  alt=""
                />
              </a>
            </li>
            <li>
              <a href="#">
                <img
                  class="social-media-icon"
                  src="@/assets/images/317712_code repository_github_repository_resource_icon.svg"
                  alt=""
                />
              </a>
            </li>
          </ul>
          <a href="#works" class="btn px-14 btn-primary btn-lg">All works</a>
        </div>
      </div>
    </div>
    <div class="container">
      <h2 id="works" class="fw-bold font-2xl mb-20">Works</h2>
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
                src="@/assets/images/317712_code repository_github_repository_resource_icon.svg"
                alt=""
              />
            </a>
          </a>
        </li>
      </ul>
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
  background: linear-gradient(#ffffff, #c9cdff);
  top: 0;
  left: 0;

  &__title {
    font-size: 92px;
    letter-spacing: 4px;
  }
}

.social-media-icon {
  width: 30px;
  height: 30px;
}
</style>
