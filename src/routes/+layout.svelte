<script>
    import {Navigation, Footer} from '$lib'
</script>

<Navigation />

<main>
	<slot />
</main>
<div class="fake-div"></div>

<Footer />

<style>
	main {
		margin: 0 14px 0 14px;
		background-color: var(--white);
		border-radius: 1.48rem;
		min-height: 200vh;
	}

	.fake-div {
		width: 100%;
		height: 14px;
		background: var(--purple);
		position: sticky;
		bottom: 0;
	}
	
	.fake-div::before {
		content: '';
		position: absolute;
		left: 14px;
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at right top, transparent 1.48rem, var(--purple) 1.48rem)
			border-box;
	}

	.fake-div::after {
		content: '';
		position: absolute;
		right: 14px;
		bottom: 100%;
		width: var(--radius);
		height: var(--radius);
		background: radial-gradient(circle at left top, transparent 1.48rem, var(--purple) 1.48rem)
			border-box;
	}
</style>
