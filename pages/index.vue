<template>
  <div class="index-page">
    <img 
      src="/img/tree-branch.png" 
      alt="tree-branch" 
      class="index-page__tree-branch" 
    />
    <theHeader class="index-page__header" />

    <main class="index-page__content wrapper">
      <section class="index-page__content-inside">
        <General class="index-page__content-item" />
        <About class="index-page__content-item" />
      </section>
    </main>
  </div>
</template>

<script>
import theHeader from '../components/site/theHeader';
import General from '../components/sections/general';
import About from '../components/sections/about';

export default {
  components: {
    theHeader,
    General,
    About
  },
  data() {
    return {
      
    }
  },

  name: 'IndexPage'
}
</script>

<style lang="scss">
.index-page {
  &__header {
    position: fixed;
    top: 0;
    z-index: 10;
  }

  &__content {
    background: $pink--general;
  }

  &__content-inside {
    max-width: 1440px;
    margin: 0 auto;
    background: $pink--light;
    border-radius: 50px;
    position: relative;
  }

  &__content-item {
    padding-bottom: 100px;

    &:first-child {
      padding-bottom: 172px;
    }
  }

  &__tree-branch {
    position: absolute;
    top: 0;
    right: 0;
    z-index: 11;
  }
}

body {
  margin: 0 auto;
}
</style>
