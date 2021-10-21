<template>
  <div>
    <nav class="d-flex justify-content-between my-10 container">
      <h1 class="font-l">
        <NuxtLink to="/">Alysa Chan</NuxtLink>
      </h1>
      <ul class="d-flex">
        <li class="me-16">
          <a class="fw-medium text-uppercase" href="#">works</a>
        </li>
        <li class="me-16">
          <a class="fw-medium text-uppercase" href="#">articles</a>
        </li>
        <li>
          <a class="fw-medium text-uppercase" href="#">about</a>
        </li>
      </ul>
    </nav>
    <Nuxt />
  </div>
</template>

<script>
export default {}
</script>

<style>
nav {
  z-index: 10;
}
</style>
