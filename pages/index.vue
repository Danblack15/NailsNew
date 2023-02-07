<template>
  <div class="index-page">
    <theHeader class="index-page__header" />

    <main class="index-page__content wrapper">
      <section class="index-page__content-inside" v-if="isInit">
        <General class="index-page__content-item" />
        <About class="index-page__content-item" />
        <Portfolio class="index-page__content-item"/>
        <Price class="index-page__content-item"/>
      </section>
    </main>

    <img 
      src="/img/tree-branch.png" 
      alt="tree-branch" 
      class="index-page__tree-branch" 
      v-if="isInit"
    />
  </div>
</template>

<script>
import theHeader from '@/components/site/theHeader'
import General from '@/components/sections/general'
import About from '@/components/sections/about'
import Portfolio from '@/components/sections/portfolio'
import Price from '@/components/sections/price'

export default {
  components: {
    theHeader,
    General,
    About,
    Portfolio,
    Price
  },

  data() {
    return {
      isInit: false
    }
  },

  mounted() {
    this.isInit = true
  },

  name: 'IndexPage'
}
</script>

<style lang="scss">
.index-page {
  overflow-x: hidden;
  &__header {
    position: fixed;
    top: 0;
    z-index: 100;
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
    z-index: 101;

    animation-name: tree-branch;
    animation-duration: 1s;
    animation-delay: .5s;
    animation-fill-mode: forwards;
    transform: translate(40%, -30%) rotate(25deg);

    @media (max-width: $xxl) {
      width: 300px;
    }

    @media (max-width: $xl) {
      animation-name: tree-branch-tablet;
    }

    @media (max-width: $md) {
      animation-name: tree-branch-mobile;
      width: 150px;
    }
  }

  @keyframes tree-branch {
    100% {
      transform: translate(30%, -20%) rotate(0);
    }
  }

  @keyframes tree-branch-tablet {
    100% {
      transform: translate(20%, 10%) rotate(0);
    }
  }

  @keyframes tree-branch-mobile {
    100% {
      transform: translate(25%, 10%) rotate(-20deg);
    }
  }
}

body {
  margin: 0 auto;
}
</style>
