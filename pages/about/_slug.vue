<template>
  <div class="mt-21 mb-21">
    <div class="container">
      <h2 class="fw-bold font-2xl mb-20 text-uppercase">About me</h2>
      <div class="row">
        <div class="markdown-content col-7">
          <nuxt-content :document="page" />
        </div>
        <div class="col-5"></div>
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
</style>
