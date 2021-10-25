<template>
  <div>
    <div
      :class="[
        { 'bg-primary text-white': !isWindowTop || showMenu },
        'fixed-top top-nav-wrap',
      ]"
    >
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
            <NuxtLink to="/#works" class="fw-medium text-uppercase"
              >works</NuxtLink
            >
          </li>
          <li class="me-16">
            <NuxtLink to="/#articles" class="fw-medium text-uppercase"
              >articles</NuxtLink
            >
          </li>
          <li class="me-16">
            <NuxtLink to="/about" class="fw-medium text-uppercase"
              >about</NuxtLink
            >
          </li>
          <li class="me-8">
            <a href="#" target="_blank">
              <img
                :class="[
                  { 'icon--white': !isWindowTop },
                  'top-nav__social-media-icon',
                ]"
                src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                alt="linkedIn"
              />
            </a>
          </li>
          <li>
            <a href="https://github.com/alysachan830" target="_blank">
              <img
                :class="[
                  { 'icon--white': !isWindowTop },
                  'top-nav__social-media-icon',
                ]"
                src="images/317712_code repository_github_repository_resource_icon.svg"
                alt="github"
              />
            </a>
          </li>
        </ul>
        <button
          :class="[
            { 'top-nav-toggle--cross': showMenu },
            { 'border-white top-nav-toggle--white': !isWindowTop || showMenu },
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
            <li class="mb-4">
              <NuxtLink
                to="#"
                class="text-uppercase font-4xl fw-bold text-white"
              >
                Works
              </NuxtLink>
            </li>
            <li class="mb-4">
              <NuxtLink
                to="#"
                class="text-uppercase font-4xl fw-bold text-white"
              >
                Articles
              </NuxtLink>
            </li>
            <li class="mb-4">
              <NuxtLink
                to="#"
                class="text-uppercase font-4xl fw-bold text-white"
              >
                About
              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </transition>
    <div>
      <Nuxt />
      <footer class="bg-primary pt-20 pb-16">
        <div
          class="
            row
            justify-content-center
            text-center text-white
            mb-18
            w-100
            mx-auto mx-md-0
          "
        >
          <div class="col-md-8">
            <p class="font-md-4xl font-xl fw-bold">Let's get in touch!</p>
            <p class="font-md-m font-s mb-md-18 mb-10">
              I’m currently looking for a full-time junior front-end developer
              job position in Hong Kong.
            </p>
            <ul class="d-inline-block d-flex justify-content-center">
              <li class="me-10 md-md-0 mb-10">
                <a
                  href="https://github.com/alysachan830"
                  class="d-flex align-items-center"
                  target="_blank"
                >
                  <img
                    class="social-media-icon icon--white me-4"
                    src="images/317712_code repository_github_repository_resource_icon.svg"
                    alt="github"
                  />
                </a>
              </li>
              <li class="me-10 md-md-0 mb-10">
                <a href="#" class="d-flex align-items-center" target="_blank">
                  <img
                    class="social-media-icon icon--white me-4"
                    src="images/5282542_linkedin_network_social network_linkedin logo_icon.svg"
                    alt="linkedin"
                  />
                </a>
              </li>
              <li>
                <a
                  href="mailto:alysachansl@gmail.com"
                  class="d-flex align-items-center"
                >
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
        <nav
          class="
            container
            d-flex
            flex-md-row flex-column
            justify-content-between
            align-items-center
          "
        >
          <ul class="d-flex mb-8 mb-md-0">
            <li class="me-md-16 me-12 font-md-base font-s">
              <NuxtLink
                to="/#works"
                class="hover--secondary fw-medium text-uppercase text-white"
                >works</NuxtLink
              >
            </li>
            <li class="me-md-16 me-12 font-md-base font-s">
              <NuxtLink
                to="/#articles"
                class="hover--secondary fw-medium text-uppercase text-white"
                >articles</NuxtLink
              >
            </li>
            <li class="me-md-16 font-md-base font-s">
              <NuxtLink
                to="/about"
                class="hover--secondary fw-medium text-uppercase text-white"
                >about</NuxtLink
              >
            </li>
          </ul>
          <a
            href="https://github.com/alysachan830/alysa-chan-portfolio"
            class="d-flex align-items-center font-s text-white"
            target="_blank"
          >
            <img
              class="footer-icon icon--white me-3 d-none d-md-block"
              src="images/317712_code repository_github_repository_resource_icon.svg"
              alt="github"
            />
            <span class="hover--secondary">Developed by Alysa Chan</span></a
          >
          <p class="font-xs text-white">2021 © Alysa Chan</p>
        </nav>
      </footer>
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
import debounce from 'lodash/debounce'

export default {
  data() {
    return {
      isWindowTop: true,
      showMenu: false,
    }
  },
  mounted() {
    const handleScroll = debounce(this.checkScrollPosition, 300)
    window.addEventListener('scroll', handleScroll)
  },
  methods: {
    checkScrollPosition() {
      if (window.scrollY === 0) {
        this.isWindowTop = true
      } else {
        this.isWindowTop = false
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
@import '@/assets/stylesheets/all';

.top-nav {
  height: 64px;
  &-wrap {
    transition: all 0.2s;
  }

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

.social-media-icon {
  width: 28px;
}

.footer-icon {
  width: 20px;
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
