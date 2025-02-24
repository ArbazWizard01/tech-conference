<script>
	let name = '';
	let email = '';
	let phone = '';
	let subject = '';
	let message = '';
</script>

<div class="contact-container">
	<h1 class="contact-title">contact</h1>
	<p class="contact-subtitle">#have questions?</p>
	<h2 class="contact-heading">Drop us a Line</h2>

	<div class="contact-content">
		<!-- Left: Contact Form -->
		<form class="contact-form">
			<input type="text" placeholder="Your Name *" bind:value={name} required />
			<input type="email" placeholder="Your Email *" bind:value={email} required />
			<input type="tel" placeholder="Phone Number" bind:value={phone} />
			<input type="text" placeholder="Subject" bind:value={subject} />
			<textarea placeholder="Message" bind:value={message}></textarea>
			<button type="submit" class="submit-btn">📩 Send Now</button>
		</form>

		<!-- Right: Contact Details -->
		<div class="contact-details">
			<div class="contact-box">
				<p class="icon">📧</p>
				<h3>Let's Call or Email</h3>
				<p>example@EmptyCup.com</p>
				<p>+1-302-123-4567</p>
			</div>
			<div class="contact-box">
				<p class="icon">👥</p>
				<h3>Be Creative Our Team</h3>
				<p>example@EmptyCup.com</p>
				<p>+1-302-123-4567</p>
			</div>
			<div class="contact-box">
				<p class="icon">💬</p>
				<h3>Let's Chat</h3>
				<p>example@EmptyCup.com</p>
			</div>
		</div>
	</div>
</div>

<style>
	.contact-container {
		text-align: center;
		padding: 50px;
		background: #f5f5f5;
	}
	.contact-title {
		font-size: 80px;
		color: rgba(0, 0, 0, 0.1);
		position: absolute;
		top: 5%;
		left: 50%;
		transform: translateX(-50%);
		z-index: -1;
	}
	.contact-subtitle {
		color: red;
		font-size: 16px;
	}
	.contact-heading {
		font-size: 32px;
		font-weight: bold;
	}
	.contact-content {
		display: flex;
		justify-content: center;
		gap: 40px;
		margin-top: 40px;
	}
	.contact-form {
		background: white;
		padding: 20px;
		border-radius: 8px;
		box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
		display: grid;
		gap: 15px;
		width: 50%;
	}
	.contact-form input,
	.contact-form textarea {
		padding: 12px;
		border: 1px solid #ddd;
		border-radius: 5px;
		width: 95%;
		font-size: 22px;
	}
	.submit-btn {
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
		color: white;
		padding: 12px;
		border: none;
		border-radius: 5px;
		cursor: pointer;
		font-size: 22px;
	}
	.contact-details {
		background-image: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
		padding: 30px;
		border-radius: 8px;
		color: white;
		width: 30%;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}
	.contact-box {
		text-align: center;
	}
	.icon {
		font-size: 24px;
	}
</style>
