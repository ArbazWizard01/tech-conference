<script>
	import Contact from '$lib/Contact.svelte';
	import Sponsor from '$lib/Sponsor.svelte';
</script>

<section class="sponsor-intro">
	<div class="header">Sponsor List</div>
	<p class="head-line">Learn more about our EmptyCup convention Sponsors</p>
</section>

<Sponsor />
<br />
<Contact />

<style>
	.sponsor-intro {
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		height: 60vh;
		color: #f5f5f5;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding-left: 200px;
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
	}
	.header {
		font-size: 80px;
	}
	.head-line {
		font-size: 25px;
	}
	@media (max-width: 720px) {
		.sponsor-intro {
			display: block;
			padding-left: 70px;
			padding-top: 70px;
			height: 40vh;
		}
		.header {
			font-size: 40px;
		}
		.head-line {
			font-size: 20px;
			padding-top: 20px;
			max-width: 80%;
		}
	}
</style>
