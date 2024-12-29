<script lang="ts">
	import BeBold from "$lib/components/home/BeBold.svelte";
	import Header from "$lib/components/home/Header.svelte";
	import Modal from "$lib/components/home/Modal.svelte";

	let showModal = false;
	let showStickyNavbar = false; // For toggling the sticky navbar
	let currentWord = "Bold"; 
	let words = ["Bold", "Free", "Yourself", "Confident", "Colorful", "Brave"];
	let typingInterval: number;

	function toggleModal() {
		showModal = !showModal;
	}

	function startTyping() {
		let wordIndex = 0;
		let charIndex = 0;
		const typingSpeed = 100; 
		const switchSpeed = 2000;

		function typeWord() {
			if (charIndex < words[wordIndex].length) {
				currentWord = words[wordIndex].slice(0, charIndex + 1);
				charIndex++;
			} else {
				clearInterval(typingInterval);
				setTimeout(() => {
					wordIndex = (wordIndex + 1) % words.length;
					charIndex = 0;
					typingInterval = setInterval(typeWord, typingSpeed);
				}, switchSpeed);
			}
		}

		typingInterval = setInterval(typeWord, typingSpeed);
	}

	import { onMount } from "svelte";
	onMount(() => {
		startTyping();

		// Add scroll listener to toggle sticky navbar
		const handleScroll = () => {
			const beBoldSection = document.querySelector(".be-bold");
			if (beBoldSection) {
				const rect = beBoldSection.getBoundingClientRect();
				showStickyNavbar = rect.bottom <= 0; // If the section is out of view
			}
		};

		window.addEventListener("scroll", handleScroll);
		return () => window.removeEventListener("scroll", handleScroll);
	});
</script>

<!-- Main Content -->
<Header {toggleModal} />
{#if showStickyNavbar}
	<nav class="sticky-navbar">
		<div class="search-box">
			<i class="bi bi-search"></i>
			<input type="text" placeholder="Search services or businesses" />
		</div>
		<div class="menu">
			<span>Where?</span>
			<span>When?</span>
			<span>Log In / Sign Up</span>
			<span class="list-business">List your business</span>
		</div>
	</nav>
{/if}

<BeBold {currentWord} />

<Modal {showModal} {toggleModal} />

<style>
	.sticky-navbar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		background: #000;
		color: white;
		padding: 1rem;
		display: flex;
		align-items: center;
		justify-content: space-between;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		z-index: 1000;
	}

	.sticky-navbar .search-box {
		display: flex;
		align-items: center;
		background-color: #fff;
		border-radius: 50px;
		padding: 0.5rem 1rem;
		width: 300px;
	}

	.sticky-navbar .search-box i {
		color: #999;
		margin-right: 0.5rem;
	}

	.sticky-navbar .search-box input {
		border: none;
		outline: none;
		flex: 1;
		color: #333;
	}

	.sticky-navbar .menu {
		display: flex;
		gap: 1rem;
		align-items: center;
	}

	.sticky-navbar .menu span {
		cursor: pointer;
	}

	.sticky-navbar .menu .list-business {
		background: #fff;
		color: #000;
		padding: 0.5rem 1rem;
		border-radius: 20px;
		font-weight: bold;
	}
</style>
