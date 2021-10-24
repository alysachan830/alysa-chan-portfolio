<template>
  <div class="mt-21 mb-21">
    <div class="container">
      <h2 class="fw-bold text-uppercase">About me</h2>
      <nuxt-content :document="page" />
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

<style></style>
