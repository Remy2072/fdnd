<script>
	import { Navigation, Footer } from '$lib';
</script>

<Navigation />

<main>
	<slot />
</main>
<div class="fake-div"></div>

<Footer />

<style>
	main {
		margin: 0 1rem;
		background-color: var(--grey);
		border-radius: 1.48rem;
		min-height: 100vh;
	}

	@media only screen and (min-width: 768px) {
		main {
			margin: 0 var(--radius);
		}
	}

	.fake-div {
		display: none;
		width: 100%;
		height: 1rem;
		background: var(--purple);
		position: sticky;
		bottom: 0;
	}

	@media only screen and (min-width: 768px) {
		.fake-div {
			display: block;
			height: var(--radius);
		}
	}

	.fake-div::before {
		content: '';
		position: absolute;
		left: 1rem;
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at right top, transparent 1.48rem, var(--purple) 1.48rem)
			border-box;
	}

	@media only screen and (min-width: 768px) {
		.fake-div::before {
			left: var(--radius);
		}
	}

	.fake-div::after {
		content: '';
		position: absolute;
		right: 1rem;
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at left top, transparent 1.48rem, var(--purple) 1.48rem)
			border-box;
	}

	@media only screen and (min-width: 768px) {
		.fake-div::after {
			right: var(--radius);
		}
	}
</style>
