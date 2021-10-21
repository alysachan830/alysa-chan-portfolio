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
    <!-- <footer class="bg-primary pt-20 pb-12">
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
    </footer> -->
  </div>
</template>

<script>
export default {}
</script>

<style>
nav {
  z-index: 10;
}

.icon--white {
  filter: invert(1);
}

.social-media-icon {
  width: 28px;
}
</style>
