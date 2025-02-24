<script>
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';
	import Schedule from '$lib/Schedule.svelte';
	import Speaker from '$lib/Speaker.svelte';
	import Contact from '$lib/Contact.svelte';
	import About from '$lib/About.svelte';

	let speakers = [];
	let show = false;
	let eventImage;
	let scrollY = 0;

	onMount(async () => {
		show = true;
		window.addEventListener('scroll', updateScroll);
	});
	function updateScroll() {
		scrollY = window.scrollY;
	}
</script>



{#if show}
	<section class="hero">
		<div class="greet-hero" in:fly={{ y: 300, opacity: 0, duration: 1300 }}>
			<h1 class="conf-name">#Tech Conference 2025</h1>
			<p class="tagline">Accelerate Your Innovation</p>
			<ul class="time-place">
				<li>22-26 March 2025</li>
				<li>Taj Lands End</li>
			</ul>
			<a href="/" class="rgst-btn">Register Now</a>
		</div>

		<img
			class="mike"
			src="/data/images/mike.png"
			alt="mike"
			in:fly={{ x: 450, opacity: 0, duration: 1000 }}
		/>
		<img
			bind:this={eventImage}
			class="event-img"
			src="/data/images/event-shape.png"
			alt="Event Logo"
			style="transform: translateX({scrollY * 0.2}px);"
		/>
	</section>
{/if}

<Speaker />

<Schedule />

<About />
<br/>
<!-- <Contact /> -->

<style>
	
	.hero {
		position: relative;
		display: flex;
		align-items: center;
		gap: 50px;
		padding-left: 200px;
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
		color: white;
		height: 100vh;
		overflow: hidden;
		/* width: 100vw; */
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
	}

	.conf-name {
		font-size: 28px;
		color: azure;
	}
	.tagline {
		font-size: 50px;
		font-weight: 700;
		max-width: 70%;
		font-family: Arial, Helvetica, sans-serif;
	}
	.time-place {
		font-size: 24px;
		font-weight: 600;
		padding-bottom: 35px;
	}
	.rgst-btn {
		box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
		padding: 15px;
		border-radius: 10px;
		font-size: 22px;
		font-weight: 550;
		font-family: monospace;
		background-color: black;
		color: #fff;
		text-decoration: none;
		transition: all ease-in-out 300ms;
	}
	.rgst-btn:hover {
		background-color: white;
		color: black;
	}
	.mike {
		position: absolute;
		right: 150px;
		bottom: 0px;
		width: 230px;
	}
	.event-img {
		position: absolute;
		bottom: -20px;

		left: 50%;
		transform: translateX(-60%);
		width: 400px;
		transition: transform 0.3s ease-out;
	}

	@media (max-width:720px){
		.hero{
			height: auto;
			/* width: 100vw; */
			display: block;
			position: initial;
			padding: 20px;

		}
		.conf-name{
			font-size:20px;
			padding-bottom: 10px;
		}
		.mike{
			display: none;
		}
		.event-img{
			display: none;
		}
		.greet-hero{
			padding: 50px;
			
		}
		.tagline{
			font-size: 25px;
			max-width: 100%;
			padding-bottom: 30px;
		}
		.time-place{
			font-size: 20px;
			padding-bottom: 60px;
		}
	}
</style>
