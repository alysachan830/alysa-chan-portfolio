<template>
  <div>
    <nav class="d-flex justify-content-between my-10 container">
      <h1 class="font-l">
        <NuxtLink to="/">Alysa Chan</NuxtLink>
      </h1>
      <ul class="d-flex align-items-center">
        <li class="me-16">
          <a class="fw-medium text-uppercase" href="#">works</a>
        </li>
        <li class="me-16">
          <a class="fw-medium text-uppercase" href="#">articles</a>
        </li>
        <li class="me-16">
          <a class="fw-medium text-uppercase" href="#">about</a>
        </li>
        <li class="me-8">
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
    </nav>
    <Nuxt />
    <footer class="bg-primary pt-20 pb-16">
      <div class="row text-center text-white justify-content-center mb-18">
        <div class="col-md-8">
          <p class="font-md-4xl font-2xl fw-bold">Let's get in touch!</p>
          <p class="font-md-m mb-18">
            I’m currently looking for a full-time junior front-end developer job
            position in Hong Kong.
          </p>
          <ul class="d-inline-block d-flex justify-content-center">
            <li class="me-10 md-md-0 mb-10">
              <a
                href="https://github.com/alysachan830"
                class="d-flex align-items-center"
              >
                <img
                  class="social-media-icon icon--white me-4"
                  src="images/317712_code repository_github_repository_resource_icon.svg"
                  alt="github"
                />
              </a>
            </li>
            <li class="me-10 md-md-0 mb-10">
              <a href="#" class="d-flex align-items-center">
                <img
                  class="social-media-icon icon--white me-4"
                  src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                  alt="linkedin"
                />
              </a>
            </li>
            <li>
              <a href="#" class="d-flex align-items-center">
                <img
                  class="social-media-icon icon--white me-4"
                  src="images/email_black_24dp.svg"
                  alt="email"
                />
              </a>
            </li>
          </ul>
        </div>
      </div>
      <nav class="container d-flex justify-content-between align-items-center">
        <ul class="d-flex">
          <li class="me-md-16 me-12 font-md-base font-s">
            <a
              class="hover--secondary fw-medium text-uppercase text-white"
              href="#"
              >works</a
            >
          </li>
          <li class="me-md-16 me-12 font-md-base font-s">
            <a
              class="hover--secondary fw-medium text-uppercase text-white"
              href="#"
              >articles</a
            >
          </li>
          <li class="me-md-16 me-12 font-md-base font-s">
            <a
              class="hover--secondary fw-medium text-uppercase text-white"
              href="#"
              >about</a
            >
          </li>
        </ul>
        <p class="font-xs text-white">2021 © Alysa Chan</p>
      </nav>
    </footer>
    <transition name="fade">
      <button
        v-show="toggleScroll"
        class="scroll-to-top-btn position-fixed btn"
        @click="scrollToTop"
      >
        <span class="text-info material-icons"> arrow_upward </span>
      </button>
    </transition>
  </div>
</template>

<script>
import debounce from 'lodash/debounce'

export default {
  data() {
    return {
      toggleScroll: false,
    }
  },
  mounted() {
    const handleScroll = debounce(this.checkScrollPosition, 1000)
    window.addEventListener('scroll', handleScroll)
  },
  methods: {
    checkScrollPosition() {
      if (window.scrollY > 700) {
        this.toggleScroll = true
      } else {
        this.toggleScroll = false
      }
    },
    scrollToTop() {
      document.body.scrollTop = 0 // For Safari
      document.documentElement.scrollTop = 0 // For Chrome, Firefox, IE and Opera
    },
  },
}
</script>

<style lang="scss">
nav {
  z-index: 10;
}

.icon--white {
  transition: filter 0.3s;
  filter: invert(1);

  &:hover {
    filter: invert(80%);
  }
}

.social-media-icon {
  width: 28px;
}

.scroll-to-top-btn {
  transition: all 0.3s;
  bottom: 50px;
  right: 50px;
  background: #f2f2f2;

  &:hover {
    box-shadow: 2px 4px 10px rgba(184, 184, 184, 0.2);
    transform: translateY(-4px);
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
