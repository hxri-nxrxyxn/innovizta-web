<script lang="ts">
	import logo from '$lib/images/logo_small.png';
	import Icon from '@iconify/svelte';
</script>

<nav
	class="fixed top-0 z-50 flex w-full items-center justify-between px-2 py-4 backdrop-blur-3xl md:px-20"
>
	<div class="flex items-center gap-2">
		<img src={logo} alt="Innovizta Technologies Logo" class="" />
		<h5 class="text-lg font-semibold text-slate-100">Innovizta Technologies</h5>
	</div>
	<div class="hidden gap-10 text-sm text-slate-300 md:flex">
		<a href="/#cloud" class="flex items-center justify-center gap-2"
			><Icon icon="ph:cloud-fill" width={20} /> Cloud</a
		>
		<a
			href="/#projects"
			class="flex items-center justify-center gap-2"
		>
			<Icon icon="ph:kanban-fill" width={20} /> Projects
		</a>
	</div>
	<div class="flex items-center justify-center gap-6 text-sm text-slate-300">
		<a
			href="tel:+919656996744"
			class="flex items-center gap-2 rounded-full bg-slate-800 px-3 py-2 text-xs font-medium text-slate-300 ring-1 ring-slate-500 transition-all duration-500 hover:bg-slate-700/70 sm:text-sm"
			><Icon icon="ph:paper-plane-tilt-fill" width={20} /> Contact Us</a
		>
	</div>
</nav>

<style>
	a {
		@apply transition-all duration-500;
	}
	a:hover {
		@apply text-slate-400;
	}
</style>
