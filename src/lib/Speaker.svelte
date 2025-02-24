<script>
	import { onMount } from 'svelte';

	let speakers = [];

	onMount(async () => {
		const res = await fetch('/data/speakers.json');
		speakers = await res.json();
	});
</script>

<section class="speakers">
	<div class="bg-speaker">SPEAKERS</div>
	<div class="greet-speaker">
		<div class="ev-speaker">#Thought leadership</div>
		<p class="speaker-line">Join the world's leading companies<br />at Technology Conference</p>
	</div>
</section>

<section class="speakers">
	<div class="grid">
		{#each speakers as speaker}
			<div class="card">
				<img src={'/data/' + speaker.image} alt={speaker.name} />
				<h3>{speaker.name}</h3>
				<p><strong>{speaker.title}</strong></p>
				<p>{speaker.bio}</p>
			</div>
		{/each}
	</div>
</section>

<style>
	.bg-speaker {
		position: absolute;
		top: 5%;
		left: 50%;
		opacity: 50%;
		transform: translateX(-50%);
		text-align: center;
		letter-spacing: -4px;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		font-size: 120px;
		color: rgba(0, 0, 0, 0.1); /* Faded gray */
		z-index: 1;
	}
	.greet-speaker {
		display: grid;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		/* align-items: center; */
		text-align: center;
		justify-content: center;
		width: 100%;
		font-size: 22px;
		font-weight: 600;
		padding-top: 60px;
		text-align: center;
		z-index: 2;
	}
	.ev-speaker {
		color: orangered;
	}
	.speaker-line {
		font-size: 40px;
	}

	.speakers {
		position: relative;
		height: min-content; 
		display: flex;
		background: #f5f5f5;
		padding: 50px 0;
	}
	.grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr); /* 3 cards per row */
		grid-template-rows: repeat(2, auto); /* 2 rows */
		gap: 40px;
		justify-content: center;
		align-items: center;
		z-index: 2;
		width: 80%; /* Ensures proper alignment */
		margin: 0 auto;
	}
	.card {
		background: #fff;
		padding: 1rem;
		text-align: center;
		border-radius: 8px;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
		transition: all ease-in-out 300ms;
	}
	.card img {
		width: 100%;
		border-radius: 8px;
		transition: ease-in-out 300ms;
	}
	.card:hover{
		background: #f5f5f5;
	}
	.card:hover{
		transform: scale(1.05);
	}
	@media (max-width:720px) {
		.bg-speaker{
			font-size: 60px;
		}
		.speaker-line{
			font-size: 24px;
		}
		.grid{
			grid-template-columns: 1fr;
		}
	}
</style>
