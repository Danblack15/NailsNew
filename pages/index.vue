<template>
  <div class="index-page">
    <theHeader />

    <main class="index-page__content wrapper">
      <h1>Намитова Александра</h1>
    </main>
  </div>
</template>

<script>
import theHeader from '../components/site/theHeader.vue';
export default {
  components: {
    theHeader
  },

  name: 'IndexPage'
}
</script>

<style lang="scss">
.index-page {
  &__content {
    background: $pink--general;
  }
}

body {
  margin: 0 auto;
}
</style>
