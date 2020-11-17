<script>
	import * as animateScroll from "svelte-scrollto";
	import { stores } from '@sapper/app';
	import Icon from 'fa-svelte';
	import { faBars } from '@fortawesome/free-solid-svg-icons/faBars';
	import { faHome } from '@fortawesome/free-solid-svg-icons/faHome';

	// Check if currently in Audio route
	let inAudio = false;
	const { page } = stores();
	$: inAudio = $page.path.includes("Audio");
	
	// Create fontawesome icons
	let bars = faBars;
	let home = faHome;

	//slide in menu controls
	let menuVisible = false;
	const toggleMenu = () => {
		if (!stdMenu){
			menuVisible = !menuVisible;
		}
	};

	//checking scroll location
	let isUp = true;
	let y = 0;
	let wh = 0;
	$: isUp = y < wh/2;

	$: stdMenu = isUp && !inAudio;

</script> 

<svelte:window bind:scrollY={y} bind:innerHeight={wh}/>

<nav class:nav-std="{stdMenu}" class:nav-hmb="{!stdMenu}">
	<div class="logo" class:invisible="{!stdMenu}">
		{#if !inAudio}
			<a href="/#" on:click={() => animateScroll.scrollToTop()}><img src="./img/logo1.png" alt="audio pirtis"></a>
		{:else}
			<a href="/#"><img  src="./img/logo1.png" alt="audio pirtis"></a>
		{/if}
	</div>
	<div class:links="{!stdMenu}" class:visible="{menuVisible}">
		<div class="home-icon" class:invisible="{stdMenu}">
			{#if !inAudio}
				<a href="/#" on:click={() => animateScroll.scrollToTop()}><Icon icon={home}/></a>
			{:else}
				<a href="/#"><Icon icon={home}/></a>
			{/if}
		</div>
		<div class="text-links" class:text-links-hmb="{!stdMenu}">
			<span>
				{#if !inAudio}
					<a href="#apie" on:click={() => animateScroll.scrollTo({element: '#apie'})}>apie</a>
				{:else}
					<a href="#apie">apie</a>
				{/if}
				|
				{#if !inAudio}
					<a href="#klausyti" on:click={() => animateScroll.scrollTo({element: '#klausyti'})}>klausyti</a>
				{:else}
					<a href="#klausyti">klausyti</a>
				{/if}
				|
				{#if !inAudio}
					<a href="#mes" on:click={() => animateScroll.scrollTo({element: '#mes'})}>mes</a>
				{:else}
					<a href="#mes">mes</a>
				{/if}
			</span>
		</div>
	</div>
	<div class="hamburger" on:click={toggleMenu} class:invisible="{stdMenu}"><Icon icon={bars}/></div>
</nav>

<style>

	nav {
		text-align: right;
		width: 18vw;
		position: fixed;
		line-height: 2.5vw;
		top: 30vh;
		left: 7vw;
		z-index: 10;
	}

	img {
		width: 100%;
	}

	a {
		text-decoration: none;
	}

	.text-links {
		font-size: 2vw;
		padding: 0;
	}

	.hamburger {
		display: none;
	}

	.home-icon {
		display: none;
	}

	@media (max-width: 576px) {
		.nav-std {
			width: 30vw;
			position: absolute;
		}

		.nav-hmb {
			position: fixed;
			display: flex;
			width: 100%;
			justify-content: space-between;
			top: 3vh;
			left: 0;
		}

		.text-links {
			font-size: 3.4vw;
			margin-top: 10px;
		}

		.links {
			position: relative;
			display: flex;
			width: 80%;
			left: -300px;
			transition: 0.1s;
		}

		.visible {
			left: 10px;
		}

		.home-icon {
			display: inline-block;
			padding-right: 5px;
			font-size: 5vw;
		}

		.text-links-hmb {
			display: inline-block;
			margin: 0;
			font-size: 5vw;
			padding-left: 10px;
			padding-top: 5px;
		}

		.hamburger {
			position: relative;
			display: inline-block;
			font-size: 7vw;
			width: 10%;
			padding-right: 20px;
			cursor: pointer;
		}		

		.invisible {
			display: none;
		}
	}

</style>