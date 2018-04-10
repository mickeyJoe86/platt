<template>
  <ul class="nav-list">
    <li v-for="(item, i) in navList"
      :key="i"
      v-bind:class="{ 'lead-item': i === 0 }"
      class="nav-list-item">
      <a href="#" class="nav-list-item-link">
        <img
          class="nav-list-item-link-img"
          :src="item.iconPath" />
          {{ item.text }}
        <img
          class="nav-list-item-link-img"
          src="assets/icons/black/ic_arrow_forward.png" />
      </a>
    </li>
  </ul>
</template>

<script>
const iconRootPath = 'assets/icons/black/'
export default {
  name: 'PlattNavList',
  data () {
    return {
      navList: [
        {
          text: 'Shop all categories',
          iconPath: `${iconRootPath}ic_categories.png`
        },
        {
          text: 'My catalog',
          iconPath: `${iconRootPath}ic_playlist_add_check.png`
        },
        {
          text: 'My List',
          iconPath: `${iconRootPath}ic_list.png`
        },
        {
          text: 'Live Help',
          iconPath: 'assets/icons/green/ic_chat-active.png'
        },
        {
          text: 'PIM',
          iconPath: `${iconRootPath}ic_check_circle.png`
        },
        {
          text: 'Account',
          iconPath: `${iconRootPath}ic_place.png`
        },
        {
          text: 'Branch Locations',
          iconPath: `${iconRootPath}ic_place.png`
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import "../../scss/index";
.nav-list {
  padding: 16px 10px;

  &-item {
    border-top: solid 1px $borderColorGray;
    padding: 0 32px 0 16px;

    &-link {
      @include link-primary-dark;
      display: block;
      padding: 12px 0 12px 0;
      font-size: 1.1em;
      height: 100%;
      width: 100%;
      font-weight: lighter;

      &-img:first-of-type {
        margin-right: 8px;
      }
      &-img:last-of-type {
        float: right;
      }
    }

    &.lead-item {
      border: none;
      padding-bottom: 18px;

      .nav-list-item-link {
        font-weight: 800;
      }
    }
  }
}
//Medium
@media only screen and (min-width: 768px) {
  .nav-list {
    border: solid 1px $borderColorGray;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    padding: 0;

    &-item {
      padding-left: 0;
      padding-right: 0;
      width: 33%;
      text-align: center;
      border-left: solid 1px $borderColorGray;

      &-link {
        &-img:last-of-type {
          display: none;
        }
      }

      &.lead-item {
        padding: 10px 0;
        width: 100%;
      }
    }
  }
}
</style>
