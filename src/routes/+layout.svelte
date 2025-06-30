<script lang="ts">
	export const prerender = true;

	import Header from '$lib/components/Header.svelte';
	import './styles.css';
	import logo from '$lib/images/logo_small.png';
	import { onMount } from 'svelte';

	function handleAnchorClick(event: any) {
		event.preventDefault();
		const link = event.currentTarget;
		const anchorId = new URL(link.href).hash.replace('#', '');
		const anchor = document.getElementById(anchorId);
		if (!anchor) return;
		window.scrollTo({
			top: anchor.offsetTop - 100,
			behavior: 'smooth'
		});
	}

	let animate = false;
	onMount(() => {
		animate = true;
		const anchors = document.querySelectorAll('a[href^="#"]');
		anchors.forEach((anchor) => {
			anchor.addEventListener('click', handleAnchorClick);
		});
	});
</script>

{#if animate}
	<div class="min-h-screen w-full bg-slate-900">
		<Header />

		<main>
			<slot />
		</main>

		<footer class="mt-20 flex min-h-fit flex-col bg-slate-800 px-5 pb-4 pt-10 md:px-20">
			<div class="flex flex-col gap-5 md:flex-row md:gap-40">
				<div class="flex h-10 flex-row items-center justify-center gap-2">
					<img src={logo} alt="Innovizta Technologies Logo" />
					<h5 class="text-xl font-semibold text-slate-100">Innovizta Technologies</h5>
				</div>

				<div class="flex flex-col gap-4 p-4 text-slate-300">
					<b>Navigate</b>
					<div class="flex flex-col gap-2 text-sm">
						<a href="#">Home</a>
						<a href="#cloud">Cloud GPU</a>
						<a href="#services">Services</a>
					</div>
				</div>

				<div class="flex flex-col gap-4 break-all p-4 text-slate-300">
					<b>Contact Us</b>
					<div class="flex flex-col gap-2 text-sm">
						<a href="mailto:support@innoviztatechnologies.com"
							>General & Project Inquiries: <br /><span class="text-slate-400"
								>support@innoviztatechnologies.com</span
							></a
						>
					</div>
				</div>
			</div>

			<hr class="mt-4 border-slate-700" />

			<div class="mt-3 flex flex-row items-center justify-center text-sm text-slate-400">
				Copyright © {new Date().getFullYear()} 
				<a href="#">Innovizta Technologies</a>. All Rights Reserved.
			</div>

			<!-- <div class="flex flex-col gap-4 p-4 text-slate-300">
			<b>Legal</b>
			<div class="flex flex-col gap-2 text-sm">
				<a href="">Privacy Policy</a>
				<a href="">Terms of Service</a>
			</div>
		</div> -->
		</footer>
	</div>
{/if}

<style>
	a {
		@apply transition-all duration-500;
	}
	a:hover {
		@apply text-slate-500;
	}
</style>
