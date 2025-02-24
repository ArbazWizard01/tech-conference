<script>
	import { onMount } from 'svelte';
	

	let sponsor = [];

	onMount(async () => {
		const res = await fetch('/data/sponsor.json');
		sponsor = await res.json();
	});
</script>

<section class="sponsor-intro2">
	<div class="bg-sponsor">SPONSORS</div>
	<div class="greet-sponsor">
		<div class="ev-sponsor">#Thought leadership</div>
		<p class="sponsor-line">Join the world's leading companies<br />at Technology Conference</p>
	</div>
	<section class="sponsor-container">
		<div class="sponsor-cat">Gold Sponsors</div>

		<div class="sponsors">
			{#each sponsor.slice(0,3) as item}
				<img class="sponsor-img" src={item.image} alt="sponsor" />
			{/each}
		</div>
        <div class="sponsor-cat">Premium Sponsors</div>
        <div class="sponsors">
			{#each sponsor.slice(3, 4) as item}
				<img class="sponsor-img" src={item.image} alt="sponsor" />
			{/each}
		</div>
        <button class="sponsor-btn">Become a Sponsor</button>
	</section>
</section>


<style>
	.sponsor-intro2 {
		position: relative;
		height: 100vh; /* Full viewport height */
		display: flex;
		flex-direction: column;
		background: #f5f5f5; /* Grayish background */
		padding: 50px 0;
	}
	.bg-sponsor {
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
	.greet-sponsor {
		display: flex;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		font-size: 22px;
		font-weight: 600;
		padding-top: 60px;
		text-align: center;
		z-index: 2;
	}
	.ev-sponsor {
		color: orangered;
	}
	.sponsor-line {
		font-size: 40px;
	}
	.sponsor-container {
        height: max-content;
		display: grid;
		justify-content: center;
		gap: 35px;
        padding: 30px;
        background-color: #f5f5f5;
	}
    .sponsor-cat{
        text-align: center;
        font-size: 35px;
        font-weight: bolder;
    }
	.sponsor-img {
		width: 140px;
	}
    .sponsors{
        display: flex;
        justify-content: center;
        gap: 10px;
    }
    .sponsor-btn{
        padding: 20px;
        border-radius: 20px;
        font-size: 18px;
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
        transition: ease-in-out 300ms;
    }
    .sponsor-btn:hover{
		background-image: linear-gradient(120deg, #fda085 0%,  #f6d365 100%);
    }
</style>
