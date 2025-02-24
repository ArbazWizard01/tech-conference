<script>
	import About from '$lib/About.svelte';
	import Contact from '$lib/Contact.svelte';
</script>

<section class="about-intro">
	<div class="header">About Event</div>
	<p class="head-line">Get the latest info about EmptyCup</p>
</section>
<About />

<Contact />
<style>
	.about-intro {
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		height: 50vh;
		color: #f5f5f5;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding-left: 200px;
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
	}
	.header {
		font-size: 70px;
	}
	.head-line {
		font-size: 25px;
	}
</style>
