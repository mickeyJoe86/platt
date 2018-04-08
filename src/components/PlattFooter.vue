<template>
	<footer class="footer">
		<div class="footer-panel">
			<p class="footer-panel-content">Support Center</p>
			<p class="footer-panel-content">800-25-Platt</p>
			<p class="footer-panel-content">800-257-5288</p>
		</div>
		<div class="footer-panel">
			<p class="footer-panel-content">4 a.m. - 12 a.m. (pst)</p>
			<p class="footer-panel-content">7 Days a week</p>
		</div>
		<div class="footer-panel">
			<button class="footer-panel-button">
				<img class="footer-icon" src="/assets/icons/black/ic_comment.png" />
				Live Help
			</button>
		</div>
		<div class="footer-panel">
			<a class="footer-panel-link" href="">Contact Us</a>
			<a class="footer-panel-link" href="">What's New</a>
			<a class="footer-panel-link" href="">FAQ's</a>
		</div>
	</footer>
</template>

<script>
export default {
  name: 'PlattFooter'
}
</script>

<style lang="scss">
@import "../scss/index";
.footer {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 22px 0;
  background-color: $primaryBackgroundDark;
  color: #fff;

  .footer-panel {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 16px 0;
		padding: 0 20px;

		.footer-panel-content {
			font-size: 1.2em;
		}

    .footer-panel-link {
      @include link-primary;
      width: 32%;
      font-size: 1.1em;
    }

    .footer-panel-button {
			@include button-primary;
			width: 61%;
    }

    &:last-of-type {
      width: 100%;
			justify-content: space-between;
			flex-direction: row;
    }
  }
}
</style>
