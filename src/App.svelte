<script>
	import { cards } from "./data/features-card";
	import Card from "./components/card.svelte";
</script>

<style type="text/scss">
	@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;400;600&display=swap");

	$font-weight-light: 200;
	$font-weight-medium: 400;
	$font-weight-bold: 600;

	$very-dark-blue: hsl(234, 12%, 34%);
	$grayish-blue: hsl(229, 6%, 66%);
	$very-light-gray: hsl(0, 0%, 98%);

	* {
		font-family: "Poppins", sans-serif;
	}

	:global(body) {
		background-color: $very-light-gray;
	}

	:global(.txt-grayish-blue) {
		color: $grayish-blue;
	}

	:global(.txt-very-dark-blue) {
		color: $very-dark-blue;
	}

	.txt-weight-light {
		font-weight: $font-weight-light;
	}

	.txt-weight-bold {
		font-weight: $font-weight-bold;
	}

	.container {
		width: 32%;
		margin: 0 auto;
		text-align: center;
	}

	.features-container {
		padding: 0 10%;
		margin: 4rem auto;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-template-rows: repeat(4, 115px);
		grid-gap: 1rem;

		.item-1 {
			grid-row: 2 / 4;
			grid-column: 1;
		}

		.item-2 {
			grid-row: 1 / 3;
			grid-column: 2;
		}

		.item-3 {
			grid-row: 3 / 5;
			grid-column: 2;
		}

		.item-4 {
			grid-row: 2 / 4;
			grid-column: 3;
		}
	}

	@media screen and (max-width: 375px) {
		.container {
			width: 100%;
			margin: 0 auto;
			text-align: center;
		}

		.features-container {
			display: grid;
			grid-template-columns: 1fr;
			grid-template-rows: repeat(4, 1fr);
			grid-gap: 1rem;
		}

		.item-1 {
			grid-column: 1 !important;
			grid-row: 1 !important;
		}

		.item-2 {
			grid-column: 1 !important;
			grid-row: 2 !important;
		}

		.item-3 {
			grid-column: 1 !important;
			grid-row: 3 !important;
		}

		.item-4 {
			grid-column: 1 !important;
			grid-row: 4 !important;
		}
	}

	@media screen and (min-width: 370px) and (max-width: 768px) {
		.container {
			width: 82%;
			margin: 0 auto;
			text-align: center;
		}

		.features-container {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			grid-template-rows: 1fr;
			grid-gap: 1rem;
		}

		.item-1 {
			grid-column: 1 !important;
			grid-row: 1 !important;
		}

		.item-2 {
			grid-column: 2 !important;
			grid-row: 1 !important;
		}

		.item-3 {
			grid-column: 1 !important;
			grid-row: 2 !important;
		}

		.item-4 {
			grid-column: 2 !important;
			grid-row: 2 !important;
		}
	}
</style>

<main>
	<div class="container">
		<h1 class="txt-weight-light txt-very-dark-blue">
			Reliable, efficient delivery
		</h1>
		<h1 class="txt-weight-bold txt-very-dark-blue">
			Powered by Technology
		</h1>
		<p class="txt-grayish-blue">
			Our Artificial Intelligence powered tools use millions of project
			data points to ensure that your project is successful
		</p>
	</div>

	<div class="features-container">
		{#each cards as { id, title, detail, imageUri, colorHighlight }}
			<div class={'item-' + id}>
				<Card {title} {detail} {imageUri} {colorHighlight} />
			</div>
		{/each}
	</div>
</main>
