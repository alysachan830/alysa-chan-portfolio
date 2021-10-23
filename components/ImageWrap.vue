<template>
  <div>
    <div class="row mb-lg-18">
      <div
        v-for="image in images"
        :key="image.url"
        :class="`${divided} mb-18 mb-md-0`"
      >
        <figure>
          <figcaption v-if="image.caption" class="text-info font-s mb-3">
            {{ image.caption }}
          </figcaption>
          <img :src="image.url" alt="work image" />
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isResponsive: {
      type: Boolean,
      default: true,
    },
    images: {
      type: Array,
      default: () => [],
    },
  },
  computed: {
    divided() {
      return this.isResponsive
        ? `col-md-${12 / this.images.length}`
        : `col-${12 / this.images.length}`
    },
  },
}
</script>

<style></style>
