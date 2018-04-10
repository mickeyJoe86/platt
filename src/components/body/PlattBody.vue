<template>
  <main class="main">
    <section class="main-buttons">
      <PlattMainButton v-for="(button, i) in mainButtons"
        :key="i"
        :iconSrc="button.src"
        :label="button.title" />
    </section> 

    <section class="main-markets">
      <p class="main-markets-title">Product Markets</p>
      <div class="main-markets-container">
        <PlattTile v-for="(tile, i) in marketTiles"
          :key="i">
          <template slot="mediaBackground">
            <img :src="tile.src" />
          </template>
          <template slot="title">
            <p>{{ tile.title }}</p>
          </template>
        </PlattTile>  
      </div>
    </section> 

    <section class="main-promos">
      <PlattCard>
        <template slot="promo">
          <a href="#">
            <img :src="'assets/img/panel/deal.png'">
          </a>
        </template>
      </PlattCard>
      <PlattCard>
        <template slot="mediaBackground">
          <img :src="'assets/img/platt-plus.png'">
        </template>
        <template slot="title">
          <p class="headline">Get Started Today</p>
          <p class="headline">Become a <a href="#">Platt Plus</a> Member.</p>
          <button class="button-primary">Learn More</button>
          
        </template>
      </PlattCard>
      <PlattCard>
        <template slot="recentHeader">
          <div>Recently Viewed</div>
          <div><a href="#">View all</a></div>
        </template>
        <template slot="recentItems">
          <img :src="'assets/img/recent/11.png'">
          <img :src="'assets/img/recent/22.png'">
          <img :src="'assets/img/recent/22.png'">
        </template>
      </PlattCard>
    </section>

    <section class="main-tiles-container">
      <PlattTile v-for="(tile, i) in tiles"
        :key="i">
        <template slot="mediaBackground">
          <img :src="tile.src" />
        </template>
        <template slot="title">
          <p>{{ tile.title }}</p>
        </template>
      </PlattTile> 
    </section>

    <section class="main-mobile-banner">
      <PlattCard>
        <template slot="banner">
          <img :src="'assets/img/panel/app-get-banner.png'">
        </template>
        <template slot="title">
          <p class="light">Shop better, download the Platt App today</p>
        </template>
      </PlattCard>
    </section>
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
  },
  data() {
    return {
      mainButtons: [
        { title: 'Categories', src: 'assets/icons/green/ic_line_style.png'},
        { title: 'Search', src: 'assets/icons/green/ic_search.png'},
        { title: 'Scan', src: 'assets/icons/green/ic_scanner.png'}
      ],
      tiles: [
        { title: 'Super Tool Day & Dynamic Data Day', src: 'assets/img/super-tool-day.png'},
        { title: 'Branch Locations', src: 'assets/img/ic_location_b.png'},
        { title: 'Help Center', src: 'assets/img/ic_helpcenter.png'},
        { title: 'Platt University', src: 'assets/img/ic_platt-u.png'},
      ],
      marketTiles: [
        { title: 'DataComm', src: 'assets/img/datacomm.png'},
        { title: 'HVAC', src: 'assets/img/hvac.png'},
        { title: 'Industrial', src: 'assets/img/industrial.png'},
        { title: 'Lighting', src: 'assets/img/lighting.png'},
        { title: 'Energy Effeciency', src: 'assets/img/energy.png'},
        { title: 'Utility', src: 'assets/img/utility.png'},
      ]
    };
  }
};
</script>

<style lang="scss">
@import "../../scss/index";
.main {
  width: 100%;
  padding: 20px 0;
  background-color: #eee;

  &-buttons {
    width: 100%;
    display: flex;
    flex-flow: row;
    justify-content: space-evenly;
  }

  &-markets {
    width: 100%;

    &-title {
      text-align: center;
      font-weight: bold;
      font-size: 1.2em;
      color: #111;
      margin-bottom: 10px;
    }

    &-container {
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: space-around;

      .tile {
        width: 14.33%;
        height: 150px;

        &-media-background {
          height: calc(50%);
          width: 100%;
          padding: 0;
          img {
            height: auto;
          }
        }
        &-title {
          height: calc(50%);
        }
      }
    }
  }

  &-promos {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &-tiles-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;

    .tile {
      width: 45%;
    }
  }

  &-mobile-banner {
    display: flex;
    justify-content: space-around;
    width: 100%;
  }
}

//Medium
@media only screen and (min-width: 768px) {
  .main {
    &-buttons {
      display: none;
    }
    &-promos {
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-around;
      .card:nth-of-type(1) {
        order: 2;
        width: 46%;
      }
      .card:nth-of-type(2) {
        order: 1;
        width: 96%;

        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
        align-items: center;
      }
      .card:nth-of-type(3) {
        order: 3;
        width: 46%;
      }
    }
    &-tiles-container {
      .tile {
        width: 22%;
      }
    }
    &-mobile-banner {
      img {
        width: 100% !important;
      }
    }
  }
}
//Small
@media only screen and (max-width: 767px) {
  .main {
    &-markets {
      display: none;
    }
    &-promos {
      .card:nth-of-type(2) {
        height: 100%;
      }
    }
  }
}
</style>
