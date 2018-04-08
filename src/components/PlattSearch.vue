<template>
	<div class="search-container">
		<input 
			class="search-input"
			type="text" 
			name="search" 
			placeholder="What are you looking for?" />
			<span class="search-btn">
				<img src="/assets/icons/black/ic_search.png" />
			</span>	
	</div>
</template>

<script>
export default {
	name: 'PlattSearch',

}
</script>

<style lang="scss">
@import "../scss/index";

.search-container {
	padding: 15px;
	display: flex;
	flex-direction: row;

	.search-input {
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
	}

	.search-btn {		
		position: relative;
		right: 30px;
		top: 18px;
	}
}
</style>
