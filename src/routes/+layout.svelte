<script>
	import Footer from '../lib/Footer.svelte';
	import Navigation from '../lib/Navigation.svelte';
</script>

<Navigation />

<main>
	<slot />
</main>
<div class="fake-div"></div>

<Footer />

<style>
	main {
		margin: 0 var(--radius) 0 var(--radius);
		background-color: var(--white);
		border-radius: 1.48rem;
	}

	.fake-div {
		width: 100%;
		height: var(--radius);
		background: var(--purple);
		position: sticky;
		bottom: 0;
	}
	.fake-div::before {
		content: '';
		position: absolute;
		left: var(--radius);
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at right top, transparent 1.48rem, var(--base-color) 1.48rem) border-box;
	}

	.fake-div::after {
		content: '';
		position: absolute;
		right: var(--radius);
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at left top, transparent 1.48rem, var(--base-color) 1.48rem) border-box;
	}
</style>
