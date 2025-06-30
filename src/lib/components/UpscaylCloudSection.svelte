<script lang="ts">
	import IconList from './ui/IconList.svelte';
	import Input from './ui/Input.svelte';
	import { doc, setDoc } from 'firebase/firestore';
	import { waitlistCollection } from '$lib/utils/firebase';

	let name = '';
	let email = '';

	const nameRegex = /^[A-Za-z\s.'-]+$/;
	const emailRegex =
		/^[a-zA-Z0-9.!#$%&'*+\/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/;
</script>

<section
	class="mt-20 flex min-h-screen max-w-full flex-col gap-10 overflow-hidden px-4 md:px-0"
	id="cloud"
>
	<h5 class="text-center text-xs font-bold uppercase text-slate-500">Unleash Your Potential with Innovizta Cloud</h5>

	<div class="flex flex-col items-center gap-8">
		<h1 class="text-center text-3xl font-semibold text-slate-200 sm:text-5xl">
			Stop Waiting, Start Training.
		</h1>

		<p class="text-center text-slate-400 sm:max-w-2xl sm:text-xl">
			Say goodbye to hardware limitations. Innovizta Cloud provides affordable, powerful GPU compute designed for students. <br />
			Focus on learning and experimenting with ML, not on your hardware specs.
		</p>

		<div class="flex flex-col gap-3">
			<IconList icon="ph:student-fill" text="Made for Students, Priced for Students" />
			<IconList icon="ph:lightning-fill" text="Access High-Performance GPUs Instantly" />
			<IconList icon="ph:code-block-fill" text="Pre-configured with Popular ML Frameworks" />
			<IconList icon="ph:timer-fill" text="Pay-as-you-go, No Long-term Commitments" />
			<IconList icon="ph:currency-dollar-fill" text="The Most Affordable Way to Learn ML" />
			<IconList icon="ph:lifebuoy-fill" text="Full Support and Project Assistance" />
		</div>

		<div
			class="flex flex-col gap-8 rounded-3xl bg-gradient-to-t from-slate-800 to-transparent px-4 py-20 sm:px-36"
			id="get-access"
		>
			<p
				class="max-w-md rounded-lg bg-slate-600/40 p-4 text-center text-sm font-light leading-tight text-slate-300"
			>
				Ready to bring your ML projects to life without breaking the bank? <br /> Sign up now for early access and special student offers.
			</p>
			<h3 class="text-center text-3xl font-medium text-slate-300">
				Request Early Access
			</h3>

			<div class="flex flex-col gap-5">
				<div class="flex flex-col gap-4">
					<Input placeholder="Your Name" bind:value={name} type="name" />
					<Input placeholder="Your Email" bind:value={email} type="email" />
				</div>
				<button
					class="ring-ring-500 rounded-full bg-green-600 px-8 py-3 font-medium text-green-200 ring-1 ring-green-500 transition-all duration-500 hover:bg-green-500"
					on:click={async () => {
						if (name && email && name.length < 256 && emailRegex.test(email)) {
							try {
								const result = await setDoc(doc(waitlistCollection, email), {
									name,
									email
								});
							} catch (error) {
								alert(
									'Error submitting your request. Have you already registered? If not, please try again later.'
								);
								return;
							}
							alert(
								'Thank you for your interest! We will notify you as soon as access is available.'
							);
						} else {
							alert('Please fill in all the fields correctly.');
						}
					}}
				>
					Get Access
				</button>
			</div>
		</div>
	</div>
</section>
