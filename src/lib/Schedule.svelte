<script>
	import { onMount } from 'svelte';

	let schedule = [];
	let activeDay = 1; 

	
	onMount(async () => {
		const res = await fetch('/data/schedule.json');
		schedule = await res.json();
		console.log('Fetched Schedule Data:', schedule);
	});

	// Function to change active day
	function setActiveDay(day) {
		activeDay = day;
	}
</script>



<section class="schedule-intro2">
	<div class="bg-schedule">SCHEDULE</div>
	<div class="greet-schedule">
		<div class="ev-schedule">#Thought leadership</div>
		<p class="schedule-line">Join the world's leading companies<br />at Technology Conference</p>
	</div>
	<section class="schedule-container">
		<!-- Day Cards -->
		<div class="days">
			{#each Array(3)
				.fill(0)
				.map((_, i) => i + 1) as day}
				<button
					class="day-card {activeDay === day ? 'active' : ''}"
					on:click={() => setActiveDay(day)}
					on:keydown={(e) => e.key === 'Enter' && setActiveDay(day)}
					aria-label="Select schedule for Day {day}"
				>
					Day {day}
				</button>
			{/each}
		</div>

		<!-- Schedule Content -->
		{#if schedule && schedule.length > 0}
			<div class="schedule-content">
				{#each schedule.filter(event => event.day == activeDay) as session}
					<div class="schedule-item">
						<!-- Left Side: Speaker Image -->
						<img class="speaker-img" src={'/data' + session.image} alt="Speaker" />

						<!-- Right Side: Schedule Info -->
						<div class="schedule-info">
							<h3>{session.title}</h3>
							<p>{session.about}</p>
							<p><strong>Time:</strong> {session.time}</p>
							<p><strong>Room:</strong> {session.room}</p>
						</div>
					</div>
				{/each}
			</div>
		{:else}
			<p>Loading schedule...</p>
		{/if}
	</section>
</section>

<style>
	
	.schedule-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 40px;
		background: #f5f5f5;
	}

	.days {
		display: flex;
		gap: 20px;
		margin-bottom: 30px;
	}

	.day-card {
		padding: 15px 25px;
		background: #ddd;
		border-radius: 10px;
		cursor: pointer;
		font-size: 18px;
		font-weight: 600;
		transition: 0.3s;
	}

	.day-card.active {
		background: #ff5722;
		color: white;
	}

	.schedule-content {
		display: flex;
		flex-direction: column;
		gap: 20px;
		width: 80%;
	}

	.schedule-item {
		display: flex;
		align-items: center;
		background: white;
		padding: 20px;
		border-radius: 10px;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
	}

	.speaker-img {
		width: 100px;
		height: 100px;
		border-radius: 50%;
		object-fit: cover;
		margin-right: 20px;
	}

	.schedule-info {
		flex: 1;
	}

	.schedule-info h3 {
		margin: 0 0 10px;
		font-size: 22px;
	}

	.schedule-info p {
		margin: 5px 0;
		font-size: 16px;
	}
	.schedule-intro2 {
		position: relative;
		min-height: 100vh; /* Full viewport height */
		display: flex;
		flex-direction: column;
		background: #f5f5f5; /* Grayish background */
		padding: 50px 0;
		padding-bottom: 180px;
	}
	.bg-schedule {
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
	.greet-schedule {
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
	.ev-schedule {
		color: orangered;
	}
	.schedule-line {
		font-size: 40px;
	}
	@media (max-width:720px) {
		
		.bg-schedule{
			font-size: 60px;
			padding-bottom: 15px;
		}
		.schedule-line{
			font-size: 22px;
		}
		.schedule-item{
			display: grid;
			justify-content: center;
		}
		.speaker-img{
			margin-left: 45px;
			margin-bottom: 10px;
		}
		.schedule-info h3{
			font-size: 14px;
			font-weight: 500;
		}
		.schedule-info p{
			font-size: 9px
		}
	}
</style>
