<template>
  <div class="index-page">
    <img 
      src="/img/tree-branch.png" 
      alt="tree-branch" 
      class="index-page__tree-branch" 
    />
    <theHeader class="index-page__header" />

    <main class="index-page__content wrapper">
      <div class="index-page__pagination">
        <div class="index-page__pagination-item" @click="$refs.fullpage.api.moveSectionUp()">
          <img 
            src="/img/icons/arrow-nav.svg" 
            alt="вверх" 
            class="index-page__pagination-up" 
        />
        </div>
        <div class="index-page__pagination-item" @click="$refs.fullpage.api.moveSectionDown()">
          <img 
            src="/img/icons/arrow-nav.svg" 
            alt="вверх" 
            class="index-page__pagination-down" 
          />
        </div>
      </div>

      <full-page 
        ref="fullpage" 
        :options="options" 
        id="fullpage" 
        class="index-page__full-page"
      >
        <div class="section element index-page__item">
          <General />
        </div>
        <div class="section element index-page__item">
          <h1>About</h1>
        </div>
        <div class="section element index-page__item">
          <h1>Portfolio</h1>
        </div>
        <div class="section element index-page__item">
          <h1>Price</h1>
        </div>
        <div class="section element index-page__item">
          <h1>Register</h1>
        </div>
      </full-page>
    </main>
  </div>
</template>

<script>
import theHeader from '../components/site/theHeader';
import General from '../components/sections/general';

export default {
  components: {
    theHeader,
    General
  },
  data() {
    return {
      options: {
        menu: "#menu",
        anchors: ['generalBlock', 'aboutBlock', 'portfolioBlock', 'priceBlock', 'regisrBlock'],
        navigation: true,
        scrollOverflow: true,
        loopTop: false,
        resize: false,
        verticalCentered: false,
      }
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

  &__full-page {
    background: $pink--light;
    border-radius: 50px;
    max-width: 1500px;
    margin: 0 auto;
  }

  &__item {
    //margin-bottom: 100px;
  }

  &__content {
    background: $pink--general;
  }

  &__pagination {
    position: absolute;
    right: 30px;
    top: 50%;
    transform: translateY(-50%);

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 186px;
  }

  &__pagination-item {
    width: 40px;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: .2s transform;
    cursor: pointer;

    &:first-child {
      &:hover {
        transform: translateY(-10px);
      }
    }

    &:last-child {
      &:hover {
        transform: translateY(10px);
      }
    }
  }

  &__pagination-down {
    transform: rotate(180deg);
  }

  &__tree-branch {
    position: absolute;
    top: 0;
    right: 0;
    z-index: 11;
  }
}

.fp-right {
  right: 24px !important;

  & a {
    display: flex !important;
    justify-content: center !important;
  }

  & ul {
    display: flex;
    flex-direction: column;
    grid-row-gap: 16px;
  }

  & li {
    width: 52px !important;
    height: 2px !important;
    margin: 0 !important;
  }

  & span {
    border-radius: 0 !important;
    width: 33px !important;
    height: 2px !important;
    margin: 0 auto !important;
    left: unset !important;
    background: $blue !important;
    transition: .2s all ease-in-out !important;
  }

  & .active span {
    width: 52px !important;
  }
}

body {
  margin: 0 auto;
}
</style>
