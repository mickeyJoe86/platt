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
            <a v-for="(navLink, i) in navLinks"
              :key="i"
              class="nav-icon"
              href="#">
              <img :src="navLink.iconSource" />
              <span v-if="navLink.notification" class="notification"></span>
            </a>
          </div>
        </div>
      </nav>
		  <PlattSearch />
    </div>
    <PlattNavList />
	</div>
</template>

<script>
import PlattSearch from "./PlattSearch";
import PlattNavList from "./PlattNavList";

export default {
  name: "PlattHeader",
  data() {
    return {
      navLinks: [
        {
          title: "Search",
          iconSource: "assets/icons/white/ic_search.png",
          notification: false
        },
        {
          title: "Cart",
          iconSource: "assets/icons/white/ic_shopping_cart.png",
          notification: false
        },
        {
          title: "Account",
          iconSource: "assets/icons/white/ic_person.png",
          notification: true
        },
        {
          title: "Menu",
          iconSource: "assets/icons/white/ic_menu.png",
          notification: false
        }
      ]
    };
  },
  components: {
    PlattSearch,
    PlattNavList
  }
};
</script>

<style lang="scss">
@import "../../scss/index";

.header {
  &-nav {
    background-color: $primaryBackgroundGreen;
    padding: 5px 10px;

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
