<script>
	import IconList from './ui/IconList.svelte';
</script>

<div
	class="relative mt-40 flex min-h-screen w-full flex-col-reverse overflow-hidden px-4 md:px-24 lg:flex-row"
	id="desktop"
>
	<div class="flex flex-col gap-8 pb-20 md:py-20">
		<h3 class="text-4xl font-semibold leading-snug text-slate-300">
			From Concept to Creation. <br /><span class="text-slate-50">Engineering Your Vision.</span>
		</h3>
		<p class="max-w-lg text-xl font-light text-slate-300">
			Innovizta Technologies is your dedicated partner in turning ambitious ideas into reality. We empower the next generation with affordable GPU cloud access for ML, build bespoke applications for clients, and engineer cutting-edge robotic solutions from the ground up.
		</p>

		<div class="flex flex-col gap-4">
			<IconList icon="ph:wifi-slash" text="Affordable Cloud GPU for ML" />
			<IconList icon="ph:list-checks" text="End-to-End Project Development" />
			<IconList icon="ph:paint-brush" text="Custom Software & App Solutions" />
			<IconList icon="ph:leaf" text="Robotics & Automation" />
		</div>
	</div>

	<div class="-right-1/4 left-1/2 lg:absolute">
		<img src="/innovizta-desktop.png" alt="A showcase of Innovizta's custom technology solutions in action" class="lg:ml-16" />
	</div>
</div>
