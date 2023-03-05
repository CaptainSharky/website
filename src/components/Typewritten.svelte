<script>
	import Typewriter from 'svelte-typewriter';
	import { fly } from 'svelte/transition';
	import { createEventDispatcher } from 'svelte';

	import 'carbon-components-svelte/css/all.css';

	const dispatch = createEventDispatcher();

	var TypewriterTime = 250;
	var Finished = false;

	const subText = () => {
		Finished = true;
	};

	function isFinished() {
		dispatch('Typewritten_Finished');
	}
</script>

<div class="typewritten">
	<Typewriter mode="cascade" keepCursorOnFinish="true" interval={TypewriterTime} on:done={subText}>
		<h1 class="typewritten">Hallo, was geht?</h1>
	</Typewriter>
</div>
{#if Finished}
	<h2 on:outroend={isFinished()} class="subText" in:fly={{ y: 50, duration: 1000, delay: 1000 }}>
		Erfahre mehr über mich!
	</h2>
{/if}

<style>
	.typewritten {
		font-family: 'Silkscreen', cursive; /* font for the typewriter text */
		font-size: clamp(1rem, 2vw + 2rem, 4rem) !important;
		size: clamp(1rem, 2vw + 1rem, 10rem);
		text-align: center;
		margin-top: 25%;
		--cursor-width: clamp(0.3rem, 1vw + 1rem, 4rem); /* width of the typewriter cursor */
		--cursor-color: var(--cds-text-01); /* color of the typewriter cursor */
	}
	.subText {
		text-align: center;
		font-size: clamp(0.5rem, 2vw + 1rem, 3.5rem);
		font-weight: 400;
	}
</style>
