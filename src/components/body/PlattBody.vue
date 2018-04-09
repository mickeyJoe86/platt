<template>
  <main class="main">
    <!-- <div>buttons</div> -->
    <section class="main-buttons">
      <PlattMainButton 
        iconSrc="/assets/icons/green/ic_line_style.png"
        label="Categories" />
      <PlattMainButton 
        iconSrc="/assets/icons/green/ic_search.png"
        label="Search" />
      <PlattMainButton 
        iconSrc="/assets/icons/green/ic_scanner.png"
        label="Scan" />
    </section>
      
    <PlattCard>
      <template slot="promo">
        <a href="#">
          <img :src="'/assets/img/panel/deal.png'">
        </a>
      </template>
    </PlattCard>

    <PlattCard>
      <template slot="mediaBackground">
        <img :src="'/assets/img/platt-plus.png'">
      </template>
      <template slot="title">
        <p class="headline">Get Started Today</p>
        <p class="headline">Become a <a href="#">Platt Plus</a> Member.</p>
      </template>
      <template slot="cta">
        <button class="button-primary">Learn More</button>
      </template>
    </PlattCard>

    <PlattCard>
      <template slot="recentHeader">
        <div>Recently Viewed</div>
        <div><a href="#">View all</a></div>
      </template>
      <template slot="recentItems">
        <img :src="'/assets/img/recent/11.png'">
        <img :src="'/assets/img/recent/22.png'">
        <img :src="'/assets/img/recent/22.png'">
      </template>
    </PlattCard>

    <PlattTile>
      <template slot="mediaBackground">
        <img :src="'/assets/img/super-tool-day.png'" />
      </template>
      <template slot="title">
        <p>Super Tool Day & Dynamic Data Day</p>
      </template>
    </PlattTile>

    <PlattTile>
      <template slot="mediaBackground">
        <img :src="'/assets/img/ic_location_b.png'" />
      </template>
      <template slot="title">
        <p>Branch Locations</p>
      </template>
    </PlattTile>

    <PlattTile>
      <template slot="mediaBackground">
        <img :src="'/assets/img/ic_helpcenter.png'" />
      </template>
      <template slot="title">
        <p>Help Center</p>
      </template>
    </PlattTile>

    <PlattTile>
      <template slot="mediaBackground">
        <img :src="'/assets/img/ic_platt-u.png'" />
      </template>
      <template slot="title">
        <p>Platt University</p>
      </template>
    </PlattTile>

    <PlattCard>
      <template slot="banner">
        <img :src="'/assets/img/panel/app-get-banner.png'">
      </template>
      <template slot="title">
        <p class="light">Shop better, download the Platt App today</p>
      </template>
    </PlattCard>
  </main>
</template>
<script>
import PlattCard from "./Card/PlattCard";
import PlattTile from "./Tile/PlattTile";
import PlattMainButton from "./MainButton/PlattMainButton";

export default {
  name: "PlattBody",
  components: {
    PlattCard,
    PlattTile,
    PlattMainButton
  }
};
</script>

<style lang="scss">
@import "../../scss/index";
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #eee;
  width: 100%;
  padding: 10px 0;

  &-buttons {
    width: 100%;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-evenly;
  }
}
</style>
