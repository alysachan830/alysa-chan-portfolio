<template>
  <div>
    <div>
      <section id="works" class="mb-20 container works-section">
        <ul>
          <li
            v-for="(work, index) in workIntros"
            :key="work.title"
            class="row justify-content-between mb-20 work-item"
            :style="{ animationDelay: `${index * 0.15}s` }"
          >
            <component
              :is="work.path ? 'NuxtLink' : 'div'"
              :to="work.path ? `/works/${work.path}` : undefined"
              class="col-md-7 mb-5 mb-md-0"
            >
              <div class="img--hover--zoom">
                <img :src="work.imageUrl" :alt="work.title" />
              </div>
            </component>
            <div class="work col-md-4">
              <component
                :is="work.path ? 'NuxtLink' : 'div'"
                :to="work.path ? `/works/${work.path}` : undefined"
                class="mb-14"
              >
                <span class="mb-1 d-block font-l fw-medium">{{
                  work.title
                }}</span>
                <ul class="d-flex flex-wrap text-info">
                  <li
                    v-for="skill in work.technologies"
                    :key="skill"
                    class="me-5 font-s font-lg-base"
                  >
                    {{ skill }}
                  </li>
                </ul>
                <span class="mt-1 d-block text-info"> {{ work.year }} </span>
              </component>
            </div>
          </li>
        </ul>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const workIntros = await $content('workIntros')
      .fetch()
      .then((res) => res[0].workIntros)
      .catch(() => {
        error({ statusCode: 404, message: 'Page not found' })
      })
    return {
      workIntros,
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/stylesheets/all';

.works-section {
  margin-top: 60px;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(32px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.work-item {
  opacity: 0;
  animation: slideUp 0.6s cubic-bezier(0.22, 1, 0.36, 1) forwards;
}

</style>
