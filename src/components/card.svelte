<script>
	export let title = "loading...";
	export let detail = "loading...";
	export let imageUri;
	export let colorHighlight = "gray";
</script>

<style type="text/scss">
	.feature-card {
		position: relative;
		height: 210px;
		padding: 1rem 2rem;
		background: #ffffff;
		box-shadow: 10px 10px 30px #d1d1d1, -10px -10px 30px #ffffff;
		border-radius: 8px;

		h3 {
			margin-bottom: 0.6rem;
		}

		p {
			margin: 0;
		}

		img {
			position: absolute;
			right: 2rem;
			bottom: 1.5rem;
		}
	}
</style>

<div class="feature-card" style="border-top: solid 3px {colorHighlight};">
	<h3 class="txt-very-dark-blue">{title}</h3>
	<p class="txt-grayish-blue">{detail}</p>
	<img src={imageUri} width={60} height={60} alt />
</div>
