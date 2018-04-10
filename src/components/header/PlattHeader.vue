<template>
	<div class="header"> 
    <div class="header-nav">   
      <nav>
        <div class="header-nav-navbar">
          <div class="header-nav-navbar-brand">
            <a class="header-nav-navbar-brand-logo" href="#">
              <img src="assets/img/logo.png" alt="Platt Electric Logo" />
            </a>
          </div>
          <div class="header-nav-navbar-links">
            <a href="#" class="nav-icon">
              <img src="assets/icons/white/ic_search.png" />
            </a>
            <a href="#" class="nav-icon">
              <img src="assets/icons/white/ic_shopping_cart.png" />
            </a>
            <a href="#" class="nav-icon">
              <img src="assets/icons/white/ic_person.png" />
              <span class="notification"></span>
            </a>
            <a href="#" class="nav-icon" @click="handleMenuClick">
              <img src="assets/icons/white/ic_menu.png" />              
            </a>
          </div>
        </div>
      </nav>
		  <PlattSearch />
    </div>
    <div v-show="isMenuOpen">
      <PlattNavList />
    </div>
	</div>
</template>

<script>
import PlattSearch from "./PlattSearch";
import PlattNavList from "./PlattNavList";

export default {
  name: "PlattHeader",
  components: {
    PlattSearch,
    PlattNavList
  },
  data() {
    return {
      isMenuOpen: false
    };
  },
  methods: {
    handleMenuClick() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
};
</script>

<style lang="scss">
@import "../../scss/index";

.header {
  &-nav {
    background-color: $primaryBackgroundGreen;
    padding: 5px 20px 15px;

    &-navbar {
      display: flex;
      justify-content: space-between;

      &-brand {
        margin-top: 10px;
        width: 50%;

        &-logo {
          height: 100%;
        }
      }
      &-links {
        width: 50%;
        margin-top: 10px;
        display: flex;
        justify-content: space-between;

        .nav-icon {
          margin-right: 10px;
          height: 100%;

          .notification {
            @include notification-important;
          }
        }
      }
    }
  }
}
//Medium
@media only screen and (min-width: 768px) {
  .header {
    &-nav {
      &-navbar {
        &-links {
          justify-content: flex-end;
          a {
            margin-left: 15px;
          }
        }
      }
    }
  }
}
</style>
