<script>
	import Contact from "$lib/Contact.svelte";
	import Schedule from "$lib/Schedule.svelte";
	
</script>

<section class="schedule-intro">
	<div class="header">Schedule List</div>
	<p class="head-line">Learn more about our EmptyCup convention schedule</p>
</section>

<Schedule />

<Contact />

<style>
	
	.schedule-intro {
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
</style>
