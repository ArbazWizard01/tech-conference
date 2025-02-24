<script>
	import { page } from '$app/stores';
	import { derived } from 'svelte/store';

	const currentPath = derived(page, ($page) => $page.url?.pathname || '/');
	let isOpen = false;

	function toggleSidebar() {
		isOpen = !isOpen;
	}

	// Close sidebar when clicking outside
	function handleClickOutside(event) {
		if (isOpen && !event.target.closest('.sidebar, .hamburger')) {
			isOpen = false;
		}
	}
</script>

<svelte:window on:click={handleClickOutside} />

<div class="mobile-sidebar-container">
	<!-- Hamburger Icon -->
	<button
		class="hamburger {isOpen ? 'open' : 'close'}"
		on:click={toggleSidebar}
		aria-label={isOpen ? 'Close menu' : 'Open menu'}
	>
		<div class="hamburger-line" class:open={isOpen}></div>
		<div class="hamburger-line" class:open={isOpen}></div>
		<div class="hamburger-line" class:open={isOpen}></div>
	</button>

	<!-- Sidebar Overlay -->
	{#if isOpen}
		<div class="sidebar-overlay"></div>
	{/if}

	<!-- Sidebar -->
	<aside class="sidebar" class:open={isOpen}>
		<div class="sidebar-header">
			<h2>Menu</h2>
		</div>

		<nav class="sidebar-content">
			<!-- Add your navigation items here -->
			<a href="/" class="sidebar-item">Home</a>
			<a href="/speakers" class="sidebar-item">Speakers</a>
			<a href="/schedule" class="sidebar-item">Schedule</a>
			<a href="/sponsors" class="sidebar-item">Sponsors</a>
			<a href="/about" class="sidebar-item">About</a>
			<a href="/contact" class="sidebar-item">Contact</a>
		</nav>
	</aside>
</div>

<style>
	:global(:root) {
		--orange: #ff6b35;
		--white: #ffffff;
		--hover-bg: #fff3ed;
	}

	.hamburger {
		position: fixed;
		top: 20px;
		left: 20px;
		z-index: 1001;
		background: none;
		border: none;
		padding: 8px;
		cursor: pointer;
	}
    .hamburger.open{
        top: 15px;
        left: 200px;
    }
	.hamburger-line {

		width: 25px;
		height: 3px;
		background: var(--orange);
		margin: 4px 0;
		transition: all 0.3s ease;
	}
    
	.hamburger-line.open:nth-child(1) {
		transform: translateY(7px) rotate(45deg);
	}

	.hamburger-line.open:nth-child(2) {
		opacity: 0;
	}

	.hamburger-line.open:nth-child(3) {
		transform: translateY(-7px) rotate(-45deg);
	}

	.sidebar-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.5);
		z-index: 998;
	}

	.sidebar {
		position: fixed;
		top: 0;
		left: -250px;
		width: 250px;
		height: 100%;
		background: var(--white);
		box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
		transition: left 0.3s cubic-bezier(0.4, 0, 0.2, 1);
		z-index: 999;
	}

	.sidebar.open {
		left: 0;
	}

	.sidebar-header {
		padding: 20px;
		border-bottom: 2px solid var(--orange);
	}

	.sidebar-header h2 {
		margin: 0;
		color: var(--orange);
	}

	.sidebar-content {
		padding: 20px;
	}

	.sidebar-item {
		display: block;
		padding: 12px;
		color: #333;
		text-decoration: none;
		border-radius: 4px;
		margin-bottom: 8px;
		transition: all 0.2s ease;
	}

	.sidebar-item:hover {
		background: var(--hover-bg);
		color: var(--orange);
	}

	@media (min-width: 768px) {
		.mobile-sidebar-container {
			display: none;
		}
	}
</style>
