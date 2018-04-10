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
				<div><img class="footer-icon" src="/assets/icons/black/ic_comment.png" />Live Help</div>
			</button>
		</div>
		<div class="footer-panel">
			<a class="footer-panel-link" href=""><span>Contact Us</span></a>
			<a class="footer-panel-link" href=""><span>What's New</span></a>
			<a class="footer-panel-link" href=""><span>FAQ's</span></a>
		</div>
	</footer>
</template>

<script>
export default {
  name: "PlattFooter"
};
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

  &-panel {
    display: flex;
    flex-direction: column;
    align-items: center;
		margin: 16px 0;
		
    &-content {
      font-size: 1.2em;
    }

    &-link {
      @include link-primary;
      width: 32%;
      font-size: 1.1em;
    }

    &-button {
      @include button-primary;
      width: 66%;
		}

		&:nth-of-type(1) {
			p:nth-of-type(1) {
				line-height: 42px;
			}
			p:last-of-type {
				color: darken(#eee, 25%);
				font-size: .9em;
				font-weight: lighter;
			}
		}
		
		&:nth-of-type(2) {
			p {
				font-size: 1.2em;
				color: darken(#eee, 25%);
			}
		}

    &:last-of-type {
			margin-top: 40px;
      width: 100%;
      flex-direction: row;
      justify-content: center;
      text-align: center;
    }
  }
}
//Medium
@media only screen and (min-width: 768px) {
  .footer {
    &-panel {
			&-button {
				width: 33%;
			}
    }
  }
}
</style>
