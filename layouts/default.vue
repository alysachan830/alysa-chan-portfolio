<template>
  <div>
    <div class="top-nav-wrap" :class="{ 'top-nav-wrap--scrolled': !isWindowTop }">
      <nav
        class="
          top-nav
          my-auto
          d-flex
          justify-content-between
          align-items-center
          container
        "
      >
        <h1>
          <NuxtLink to="/" class="font-md-l font-m">Alysa Chan</NuxtLink>
        </h1>
        <ul class="d-flex align-items-center">
          <li class="me-16">
            <NuxtLink to="/about" class="hover hover--primary fw-medium text-uppercase">about</NuxtLink>
          </li>
          <li class="me-8">
            <a href="https://www.linkedin.com/in/alysa-chan" target="_blank">
              <img
                class="top-nav__social-media-icon"
                src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                alt="linkedIn"
              />
            </a>
          </li>
          <li>
            <a href="https://github.com/alysachan830" target="_blank">
              <img
                class="top-nav__social-media-icon"
                src="images/317712_code repository_github_repository_resource_icon.svg"
                alt="github"
              />
            </a>
          </li>
        </ul>
      </nav>
    </div>
    <div>
      <Nuxt />
      <transition name="fade">
        <button
          v-show="!isWindowTop"
          class="scroll-to-top-btn position-fixed btn"
          @click="scrollToTop"
        >
          <span class="text-info material-icons"> arrow_upward </span>
        </button>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isWindowTop: true,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isWindowTop = window.scrollY === 0
    },
    scrollToTop() {
      document.body.scrollTop = 0 // For Safari
      document.documentElement.scrollTop = 0 // For Chrome, Firefox, IE and Opera
    },
  },
}
</script>

<style lang="scss">
@import '@/assets/stylesheets/all';

.top-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  transition: background-color 0.3s ease, backdrop-filter 0.3s ease, box-shadow 0.3s ease;

  &--scrolled {
    background-color: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
  }
}

.top-nav {
  height: 64px;

  &__social-media-icon {
    height: 20px;
    width: 20px;
  }
}


.icon--white {
  transition: filter 0.3s;
  filter: invert(1);

  &:hover {
    filter: invert(80%);
  }
}


.scroll-to-top-btn {
  transition: all 0.3s !important;
  bottom: 25px;
  right: 25px;
  background-color: #f2f2f2 !important;

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
