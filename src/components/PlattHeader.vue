<template>
	<div class="header">
		<nav class="nav">
			<div class="navbar">
				<div class="nav-container">				
					<a class="nav-brand" href="#">
						<img src="/assets/img/logo.png" alt="Platt Electric Logo" />
					</a>
				</div> 
				<div class="nav-container">
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
</template>

<script>
import PlattSearch from "./PlattSearch";
export default {
  name: "PlattHeader",
  data() {
    return {
      navLinks: [
        {
          title: "Search",
					iconSource: "/assets/icons/white/ic_search.png",
					notification: false
        },
        {
          title: "Cart",
					iconSource: "/assets/icons/white/ic_shopping_cart.png",
					notification: false
        },
        {
          title: "Account",
					iconSource: "/assets/icons/white/ic_person.png",
					notification: true
        },
        {
          title: "Menu",
					iconSource: "/assets/icons/white/ic_menu.png",
					notification: false
        }
      ]
    };
  },
  components: {
    PlattSearch
  }
};
</script>

<style lang="scss">
@import "../scss/index";
.header {
  background-color: $primaryBackgroundGreen;
  padding: 5px 10px;

  .nav {
    .navbar {
      display: flex;
      justify-content: space-between;

      .nav-container {
        margin-top: 10px;
        width: 50%;

        &:last-of-type {
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
}
</style>
