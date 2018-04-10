<template>
  <div class="main-button">
    <div class="main-button-icon">
      <a href="#">
        <img :src="iconSrc" />
      </a>
    </div>
    <p class="main-button-label">{{ label }}</p>
  </div>
</template>

<script>
export default {
  name: 'PlattMainButton',
  props: ['label', 'iconSrc']
}
</script>

<style lang="scss">
@import "../../../scss/index";
.main-button {
  display: flex;
  flex-direction: column;

  &-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 75px;
    width: 75px;
    background: #fff;
    border-radius: 50%;
    box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14);

    img {
      height: 30px;
    }
  }

  &-label {
    padding: 15px 0;
    font-size: 1.1em;
    color: $buttonFontColorDark;
    text-align: center;
  }
}
</style>
