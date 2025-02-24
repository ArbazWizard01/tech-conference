

<section class="about">
	<img class="orbit" src={'/data/images/orbit.png'} alt="orbit" />
	<div class="about-content">
		<div class="about-intro2">
			<div class="ev-about">#About Event</div>
			<p class="ev-content">Get the latest info about EmptyCup</p>
			<div class="meet-speaker">
				<div class="con-i-container">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="48px"
						viewBox="0 -960 960 960"
						width="48px"
						fill="#EA3323"
						><path
							d="M38-160v-94q0-35 18-63.5t50-42.5q73-32 131.5-46T358-420q62 0 120 14t131 46q32 14 50.5 42.5T678-254v94H38Zm700 0v-94q0-63-32-103.5T622-423q69 8 130 23.5t99 35.5q33 19 52 47t19 63v94H738ZM358-481q-66 0-108-42t-42-108q0-66 42-108t108-42q66 0 108 42t42 108q0 66-42 108t-108 42Zm360-150q0 66-42 108t-108 42q-11 0-24.5-1.5T519-488q24-25 36.5-61.5T568-631q0-45-12.5-79.5T519-774q11-3 24.5-5t24.5-2q66 0 108 42t42 108ZM98-220h520v-34q0-16-9.5-31T585-306q-72-32-121-43t-106-11q-57 0-106.5 11T130-306q-14 6-23 21t-9 31v34Zm260-321q39 0 64.5-25.5T448-631q0-39-25.5-64.5T358-721q-39 0-64.5 25.5T268-631q0 39 25.5 64.5T358-541Zm0 321Zm0-411Z"
						/></svg
					>

					<h3 class="head">Meet Speaker</h3>
				</div>
				<p class="content">
					This event has dedicated tracks for every industry. Guest users can see general
					information like about top talent meet.
				</p>
			</div>
			<div class="unlimited-discuss">
				<div class="con-i-container">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="48px"
						viewBox="0 -960 960 960"
						width="48px"
						fill="#EA3323"
						><path
							d="M80-80v-740q0-24 18-42t42-18h680q24 0 42 18t18 42v520q0 24-18 42t-42 18H240L80-80Zm134-220h606v-520H140v600l74-80Zm-74 0v-520 520Z"
						/></svg
					>

					<h3 class="head">Unlimited Discuss</h3>
				</div>

				<p class="content">
					The event regularly attracts a diverse range of attendees. See general information like
					about us, event details from around the world.
				</p>
			</div>
		</div>
	</div>
	<div class="about-img">
		<img class="dot" src={'/data/images/dot.jpg'} alt="dot" />
		<img class="img1" src={'/data/images/about_1.jpeg'} alt="speaker" />
		<img class="img2" src={'/data/images/about_2.jpeg'} alt="speaker" />
	</div>
</section>



<style>
	.con-i-container{
		display: flex;
		gap: 25px;
		margin-left: -70px;
	}
	
	.orbit {
		position: absolute;
		z-index: -5;
		right: 10%;
		animation: rotate360 4s ease-in-out infinite;
	}
	@keyframes rotate360 {
		0% {
			transform: rotate(0deg);
		}
		100% {
			transform: rotate(360deg); /* Rotates right */
		}
	}
	.head {
		font-size: 30px;
	}
	.content {
		font-size: 18px;
		color: grey;
		font-weight: 500;
	}
	.about-img {
		position: relative;
		padding-top: 150px;
	}
	@keyframes rotateLeftRight {
		0% {
			transform: rotate(0deg);
		}
		50% {
			transform: rotate(-6deg); /* Rotates left */
		}
		100% {
			transform: rotate(6deg); /* Rotates right */
		}
	}

	.dot {
		position: absolute;
		z-index: -3;
		height: 380px;
		width: 450px;
		opacity: 60%;
		animation: rotateLeftRight 4s ease-in-out infinite alternate;
	}

	.img1 {
		height: 250px;
		border-top-left-radius: 20px;
	}
	.img2 {
		position: absolute;
		z-index: -1;
		left: 25%;
		top: 35%;
		height: 280px;
		border-bottom-right-radius: 20px;
	}
	
	.about {
		display: grid;
		grid-template-columns: 1fr 1fr;
		height: 100vh;
	}
	.about-content {
		
		padding: 130px;
	}
	.ev-about {
		color: orangered;
		font-size: 24px;
	}
	.ev-content {
		font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
		font-size: 45px;
		font-weight: 600;
	}

	svg {
		padding-top: 25px;
	}
	.meet-speaker,
	.unlimited-discuss {
		margin-top: 20px;
	}
	@media (max-width:720px) {
		.about{
			display: block;
		}
		
		.about-img{
			display: none;
		}
		.dot{
			display: none;
		}
		.img1{
			display: none;
		}
		.img2{
			display: none;
		}
		.content{
			font-size: 10px;
		}
		.ev-content{
			font-size: 19px;
		}
		.ev-about{
			font-size: 5px;
		}
	}
</style>
