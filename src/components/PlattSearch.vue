<template>
	<div class="search">
		<input
			class="search-input"
			type="text"
			name="search"
			placeholder="What are you looking for?" 
			@input="handleInput" />
			<span class="search-input-btn">
				<img src="/assets/icons/black/ic_search.png" />
			</span>
			<div class="search-results" v-if="results.length > 0">
				<div v-for="(result, i) in results" :key="i">{{ result.name }}</div>
			</div>
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
			if (query.length > 0 && typeof query === 'string') {		
				this.callApi(e.target.value);
			}
    }, 600),
    callApi(searchTerm) {
      this.$http
        .get(`https://swapi.co/api/people/?search=${searchTerm}`)
        .then(res => {					
					this.results = [...res.data.results]
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>

<style lang="scss">
@import "../scss/index";

.search {
  padding: 15px;
  display: flex;
  flex-direction: row;

  &-input {
    width: 100%;
    border-radius: 3px;
    height: 46px;
    border: none;
    flex: 1;
    padding-left: 20px;

    &::placeholder {
      color: #aeaeae;
      font-size: 1.4em;
    }

    &-btn {
      position: relative;
      right: 30px;
      top: 18px;
    }
	}
	
	&-results {
		position: absolute;
		top: 110px;
		width: 88%;
		background-color: #fff;
		padding: 10px 10px;
		border: 1px solid grey;
		border-radius: 3px;
	}
}
</style>
