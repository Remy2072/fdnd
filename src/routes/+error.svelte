<script>
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	onMount(() => {
		const text = document.getElementById('text');
		const setShadow = () => {
			let shadow = '';
			const maxShadows = window.innerWidth >= 700 ? 30 : 10;
			for (let i = 0; i < maxShadows; i++) {
				shadow += (shadow ? ',' : '') + -i * 1 + 'px ' + i * 1 + 'px 0 #482583';
			}
			text.style.textShadow = shadow;
		};

		setShadow();
		window.addEventListener('resize', setShadow);

		return () => {
			window.removeEventListener('resize', setShadow);
		};
	});
</script>

<section>
	<h1 id="text">De pagina is zoekgeraakt. Tijd voor een nieuwe poging!</h1>
	<h2>{$page.status}</h2>
</section>

<style>
	section {
		display: flex;
		justify-content: center;
		align-items: center;
		min-height: 100vh;
		overflow: hidden;
		box-sizing: border-box;
	}

	h1 {
		position: relative;
		color: var(--blue);
		font-weight: 700;
		font-size: 3rem;
		text-align: center;
		transform: rotate(-5deg) skew(20deg);
		transition: font-size 0.3s ease;
	}

	h2 {
		position: absolute;
		color: var(--blue);
		bottom: 0;
		right: 0;
		padding: 5rem;
		font-size: var(--radius);
	}

	@media (min-width: 700px) {
		h1 {
			font-size: 5.5rem;
		}

		h2 {
			font-size: var(--radius);
		}
	}

	@media (min-width: 1000px) {
		h1 {
			font-size: 7rem;
		}

		h2 {
			font-size: 2rem;
		}
	}

	@media (min-width: 1447px) {
		h1 {
			font-size: 10rem;
			max-width: 1400px;
		}
	}
</style>
