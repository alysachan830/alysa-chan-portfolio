<template>
  <div>
    <div class="top-nav-wrap">
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
        <ul class="d-none d-md-flex align-items-center">
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
        <button
          :class="[
            { 'top-nav-toggle--cross': showMenu },
            'top-nav-toggle d-md-none',
          ]"
          @click="showMenu = !showMenu"
        ></button>
      </nav>
    </div>
    <transition name="slide">
      <div v-show="showMenu" class="menu py-16 bg-primary d-md-none">
        <div class="container">
          <ul>
            <li>
              <a
                href="/about"
                class="text-uppercase font-md-4xl font-3xl fw-bold text-white"
                @click="showMenu = false"
              >
                About
              </a>
            </li>
          </ul>
        </div>
      </div>
    </transition>
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
      showMenu: false,
    }
  },
  methods: {
    scrollToTop() {
      document.body.scrollTop = 0 // For Safari
      document.documentElement.scrollTop = 0 // For Chrome, Firefox, IE and Opera
    },
  },
}
</script>

<style lang="scss">
@import '@/assets/stylesheets/all';

.top-nav {
  height: 64px;

  &__social-media-icon {
    height: 20px;
    width: 20px;
  }
}

.slide-enter-active {
  transition: all 0.4s ease;
}
.slide-leave-active {
  transition: all 0.4s ease;
}

.slide-enter, .slide-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(-100%);
}

.top-nav-toggle {
  border-top: 3px solid #000000;
  height: 18px;
  width: 36px;
  border-width: 3px 0 0 0;
  background: transparent;
  position: relative;

  &::before,
  &::after {
    transition: transform 0.3s;
    content: '';
    position: absolute;
    background: #000000;
    height: 3px;
    width: 100%;
    left: 0;
  }

  &::before {
    top: 6px;
  }

  &::after {
    top: 15px;
  }

  &--white {
    &::before,
    &::after {
      background: #ffffff;
    }
  }

  &--cross {
    border-top: 0px solid #000000;
    &::before {
      transform: rotate(45deg);
    }
    &::after {
      top: 6px;
      transform: rotate(135deg);
    }
  }
}

.menu {
  position: fixed;
  z-index: 20;
  top: 64px;
  bottom: 0;
  left: 0;
  right: 0;
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
