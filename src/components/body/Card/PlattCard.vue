<template>
  <div class="card">
    <div v-if="hasPromo"
      class="card-promo">
      <slot name="promo" />
    </div>
    <div v-if="hasBanner"
      class="card-banner">
      <slot name="banner" />
    </div>
    <div v-if="hasMediaBackground"
      class="card-media-background">
      <slot name="mediaBackground" />
    </div>
    <div v-if="hasRecentHeader"
      class="card-recent-header">
      <slot name="recentHeader" />
    </div>
    <div v-if="hasRecentItems"
      class="card-recent-items">
      <slot name="recentItems" />
    </div>
    <div v-if="hasTitle"
      class="card-title">
      <slot name="title" />
    </div>
    <div v-if="hasCta"
      class="card-cta">
      <slot name="cta" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'PlattCard',
  computed: {
    hasPromo () {
      return !!this.$slots.promo
    },
    hasMediaBackground () {
      return !!this.$slots.mediaBackground
    },
    hasTitle () {
      return !!this.$slots.title
    },
    hasRecentHeader () {
      return !!this.$slots.recentHeader
    },
    hasRecentItems () {
      return !!this.$slots.recentItems
    },
    hasCta () {
      return !!this.$slots.cta
    },
    hasBanner () {
      return !!this.$slots.banner
    }
  }
}
</script>

<style lang="scss" >
@import "../../../scss/index";
.card {
  margin: 10px 0;
  height: 180px;
  width: 96%;
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14);
  background-color: $primaryBackgroundLight;

  &-promo {
    height: 100%;
    img {
      height: 100%;
      width: 100%;
    }
  }

  &-banner {
    overflow: hidden;
    img {
      height: 100%;
      float: right;
    }
  }

  &-media-background {
    margin: 30px 0 20px;
    img {
      width: 100%;
    }
  }

  &-recent-header {
    padding: 16px 16px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    font-size: 1.1em;
    font-weight: bold;
    a {
      @include link-inline;
    }
  }

  &-recent-items {
    padding: 16px 16px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  &-title {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 10px 0;

    .headline {
      font-weight: bolder;
      font-size: 1.2em;
    }

    .light {
      font-weight: bold;
      font-size: 1em;
    }

    a {
      @include link-inline;
    }

    button {
      width: 66%;
      margin: 15px 0;
      @include button-secondary;
    }
  }

  &-cta {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px 0 50px;
  }
}
</style>
