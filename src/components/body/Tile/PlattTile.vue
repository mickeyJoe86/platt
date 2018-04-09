<template>
  <section class="tile">
    <div class="tile-media-background">
      <slot name="mediaBackground"></slot>
    </div>
    <div class="tile-title">
      <slot name="title"></slot>
    </div>
  </section>
</template>

<script>
export default {
  name: "PlattTile"
};
</script>

<style lang="scss">
@import "../../../scss/index";

.tile {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 200px;
  width: 45%;
  margin: 10px 0;
  box-shadow: 0 2px 2px 2px rgba(0, 0, 0, 0.14);
  background-color: #fff;

  &-media-background {
    padding: 25px 0 0;
    height: calc(66%);
    img {
      height: 90px;
    }
  }

  &-title {
    display: flex;
    align-items: center;
    justify-content: center;
    height: calc(33%);

    p {
      text-align: center;
      font-weight: bold;
      font-size: 1em;
    }
  }
}
</style>
