<script>
	import Typewritten from '../components/Typewritten.svelte';
	import { Fullpage, FullpageSection, FullpageSlide } from 'svelte-fullpage';

	import 'carbon-components-svelte/css/all.css';
	import { Theme } from 'carbon-components-svelte';
</script>

<div class="themeSelector">
	<Theme render="toggle" persist persistKey="__carbon-theme" />
</div>

<Fullpage>
	<FullpageSection title="Home" disableCentering="true">
		<Typewritten />
	</FullpageSection>
	<FullpageSection title="AboutMeSection">
		<div class="page2">
			<div><h1>Ich Bin Jakob!</h1></div>
			<div class="subText">17. Jahre alt</div>
			<div class="subText">
				Schüler am <a
					type="link"
					target="_blank"
					href="https://gymhaan.de"
					rel="noreferrer noopener">@Gymhaan</a
				>
			</div>
		</div>
	</FullpageSection>
	<FullpageSection title="SocialMediaSection">
		<div class="page2">
			<div><h1 style="margin-bottom: 1rem;">Social Media</h1></div>
			<div class="social">
				twitter:
				<a href="https://twitter.com/roterschwamm"> @Roterschwamm </a>
			</div>
			<div class="social">
				github:
				<a href="https://github.com/CaptainSharky"> @CaptainSharky</a>
			</div>
		</div></FullpageSection
	>
</Fullpage>

<style>
	:global(body) {
		height: 100vh;
		overflow: hidden;
	}
	.themeSelector {
		position: fixed;
		z-index: 1;
		margin-top: 2rem;
		margin-left: 2rem;
	}
	.page2 {
		font-size: clamp(0.5rem, 2vw + 1rem, 3.5rem);
		text-align: center;
	}
	.subText {
		font-size: clamp(0.5rem, 1vw + 1rem, 3.5rem);
		text-align: center;
	}
	.social {
		display: flex;
		font-size: clamp(0.5rem, 1vw + 0.5rem, 2.5rem);
	}
	a {
		text-decoration: none;
	}
	a:visited {
		color: blueviolet;
	}
	a:hover {
		color: coral;
	}
</style>
