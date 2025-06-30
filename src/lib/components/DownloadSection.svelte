<script>
	import Icon from '@iconify/svelte';
	// Removed Modal and other unused imports for cleanliness
</script>

<div class="flex flex-col gap-20 px-4 text-slate-300 md:px-24" id="services">
	<div class="flex w-full flex-col items-center gap-2 text-center">
		<h1 class="text-4xl font-semibold text-slate-200">Our Core Services</h1>
		<p class="text-lg font-light text-slate-400">Tailored solutions for every technological challenge.</p>
	</div>

	<div
		class="grid grid-cols-1 place-items-center gap-5 md:grid-cols-2 lg:grid-cols-4"
	>
		<!-- Service 1: End-to-End Project Development -->
		<a
			href="mailto:support@innoviztatechnologies.com"
			class="flex h-56 w-56 flex-col items-center justify-center gap-5 rounded-2xl bg-slate-800 p-4 text-center ring-1 ring-slate-500 transition-all duration-500 hover:scale-110 hover:bg-slate-700 md:h-64 md:w-64"
		>
			<Icon icon="ph:rocket-launch-fill" width="5rem" />
			<h5 class="text-xl font-medium">Project Development</h5>
			<p class="text-sm text-slate-400">From initial concept and planning to final deployment and support.</p>
		</a>

		<!-- Service 2: Custom App & Software Solutions -->
		<a
			href="mailto:support@innoviztatechnologies.com"
			class="flex h-56 w-56 flex-col items-center justify-center gap-5 rounded-2xl bg-slate-800 p-4 text-center ring-1 ring-slate-500 transition-all duration-500 hover:scale-110 hover:bg-slate-700 md:h-64 md:w-64"
		>
			<Icon icon="ph:puzzle-piece-fill" width="5rem" />
			<h5 class="text-xl font-medium">Personalized Solutions</h5>
			<p class="text-sm text-slate-400">Bespoke applications and software built to solve your unique problems.</p>
		</a>

		<!-- Service 3: Robotics & Automation -->
		<a
			href="mailto:support@innoviztatechnologies.com"
			class="flex h-56 w-56 flex-col items-center justify-center gap-5 rounded-2xl bg-slate-800 p-4 text-center ring-1 ring-slate-500 transition-all duration-500 hover:scale-110 hover:bg-slate-700 md:h-64 md:w-64"
		>
			<Icon icon="ph:robot-fill" width="5rem" />
			<h5 class="text-xl font-medium">Robotics Projects</h5>
			<p class="text-sm text-slate-400">Engineering intelligent systems that interact with the physical world.</p>
		</a>

		<!-- Service 4: Project Assistance -->
		<a
			href="mailto:support@innoviztatechnologies.com"
			class="flex h-56 w-56 flex-col items-center justify-center gap-5 rounded-2xl bg-slate-800 p-4 text-center ring-1 ring-slate-500 transition-all duration-500 hover:scale-110 hover:bg-slate-700 md:h-64 md:w-64"
		>
			<Icon icon="ph:lifebuoy-fill" width="5rem" />
			<h5 class="text-xl font-medium">Project Assistance</h5>
			<p class="text-sm text-slate-400">Expert guidance and hands-on help to push your student or client projects forward.</p>
		</a>
	</div>
</div>

<!-- All Modal code has been removed as it is no longer relevant to this section -->

<style>
	/* This existing style will now apply to the <a> tags, making them look like the original buttons */
	#download-links-list a {
		@apply mx-4 flex items-center justify-center gap-2 rounded-lg bg-slate-700 p-2 ring-1 ring-slate-500;
	}
</style>
