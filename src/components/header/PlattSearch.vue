<template>
	<div class="search">
		<input			
			class="search-input"
			type="text"
			name="search"
			placeholder="What are you looking for?" 
			autocomplete="off"
			@input="handleInput" 
			@blur="handleFocusOut" />
			<span class="search-input-btn">
				<img src="assets/icons/black/ic_search.png" />
			</span>
			<ul class="search-results" v-if="results.length > 0">
				<li 
					v-for="(result, i) in results"
					:key="i"
					class="search-results-item">
					<a href="#" class="search-results-item-link">{{ result.name }}</a>
				</li>
			</ul>
	</div>
</template>

<script>
import debounce from "lodash.debounce";

export default {
  name: "PlattSearch",
  data() {
    return {
      results: []
    };
  },
  methods: {
    handleInput: debounce(function(e) {
      this.results = [];
      const query = e.target.value;
      if (query.length > 0 && typeof query === "string") {
        this.callApi(e.target.value);
      }
    }, 600),
    callApi(searchTerm) {
      this.$http
        .get(`https://swapi.co/api/people/?search=${searchTerm}`)
        .then(res => {
          this.results = [...res.data.results];
        })
        .catch(err => {
          console.log(err);
        });
    },
    handleFocusOut() {
      setTimeout(() => {
        this.results = [];
      }, 200);
    }
  }
};
</script>

<style lang="scss">
@import "../../scss/index";

.search {
  display: flex;
  flex-direction: row;
  width: 100%;
	position: relative;
	margin-top: 10px;

  &-input {
    font-size: 1.1em;
    color: #626262;
    width: 100%;
    border-radius: 3px;
    height: 46px;
    border: none;
    flex: 1;
    padding-left: 20px;

    &::placeholder {
      color: #aeaeae;
    }

    &-btn {
      position: absolute;
      right: 30px;
      top: 18px;
    }
  }

  &-results {
    position: absolute;
    top: 53px;
    width: 100%;
    background-color: #fff;
    border: 1px solid grey;
    border-radius: 3px;
    max-height: 300px;
    overflow: auto;

    &-item {
      padding: 10px;
      border-top: solid 1px grey;
      &:first-of-type {
        border-top: none;
      }

      &-link {
        @include link-primary-dark;
        display: inline-block;
        width: 100%;
        height: 100%;
        display: block;
      }
    }
  }
}
</style>
