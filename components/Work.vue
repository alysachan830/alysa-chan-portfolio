<template>
  <div class="mt-21">
    <div class="container mb-16">
      <div class="row justify-content-between flex-column-reverse flex-md-row">
        <div class="col-md-8">
          <span class="font-m">
            <slot name="year"></slot>
          </span>
          <h2 class="font-2xl">
            <slot name="title"></slot>
          </h2>
        </div>
        <div class="col-md-4">
          <a class="text-info text-end mb-8 mb-md-0 font-s" href="/#works"
            >Back to works
            <span class="material-icons align-middle font-s">
              chevron_right
            </span>
          </a>
        </div>
      </div>
    </div>

    <div class="cover-img mb-21">
      <slot name="coverImg"></slot>
    </div>
    <div class="container">
      <div class="row justify-content-between mb-20 mb-md-0">
        <div class="col-md-7 content">
          <slot name="description"></slot>
        </div>
        <ul class="col-md-3">
          <li class="mb-10">
            <p class="fw-bold mb-3">URL</p>
            <slot name="url"></slot>
          </li>
          <li class="mb-10">
            <p class="fw-bold mb-3">My role</p>
            <slot name="role"></slot>
          </li>
          <li>
            <p class="fw-bold mb-3">Technologies</p>
            <slot name="technologies"></slot>
          </li>
        </ul>
      </div>
    </div>
    <div class="container content mb-18">
      <slot name="content"></slot>
    </div>
    <div class="container mb-21">
      <a class="text-info mb-8 mb-md-0 font-m text-end" href="/#works"
        >Back to works
        <span class="material-icons align-middle"> chevron_right </span>
      </a>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import '@/assets/stylesheets/all';

.cover-img {
  img {
    width: 100vw;
    height: 1280px;
  }
}

.description,
.content {
  line-height: 1.8;
  @include media-breakpoint-up(md) {
    font-size: 18px;
  }
  font-size: 16px;
}

.content {
  img {
    // height: 838px;
    width: 100%;
  }
}
</style>
