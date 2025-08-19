<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { PackageCheck, Lightbulb, LampDesk, ChevronRight } from '@lucide/svelte';
	import jessicaImg from '$lib/assets/jessica.avif';
	import heroVideo from '$lib/assets/bg.webm';

	const testimonials = [
		{
			name: 'Jessica',
			role: 'Founder, Jelly Peanut',
			image: jessicaImg,
			content:
				"Zenzak made Jelly Peanut's database easy to maintain and edit quickly."
		},
	];

	const services = [
		{
			title: 'Product Visualisation & Renders',
			description: 'Custom strategies tailored to your business goals and market position.',
			icon: LampDesk
		},
		{
			title: 'Web & Design Consulting',
			description: 'Transform your ideas into actionable business solutions.',
			icon: Lightbulb
		},
		{
			title: 'Technical & Explainer Animations',
			description: 'Scale your business with data-driven growth strategies.',
			icon: PackageCheck
		}
	];
</script>

<div class="bg-base-100 min-h-screen">
	<!-- Hero Section -->
	<section class="bg-base-200 relative min-h-[70vh] overflow-hidden p-3 py-6 lg:px-10">
		<div class="container mx-auto flex px-4">
			<div class="grid min-h-[70vh] w-full items-center gap-12 md:min-h-[60vh] lg:grid-cols-2">
				<div class="order-2 lg:order-1" in:fade={{ duration: 1000 }}>
					<h1 class="text-center text-4xl leading-tight font-bold lg:text-left lg:text-6xl">
						Innovative Visualization.<br />
						Web & Design Consulting.<br />
						Immersive 3D.
					</h1>
					<p class="text-base-content/80 mt-6 text-center text-lg lg:text-left">
						We help businesses grow through design consulting, innovative visualization solutions, and immersive 3D
						experiences. Let's build your success story together.
					</p>
					<div
						class="mt-8 flex flex-col items-center justify-center gap-4 lg:flex-row lg:justify-start"
					>
						<button class="btn btn-primary">Schedule Consultation</button>
						<button class="btn btn-outline">Our Services</button>
					</div>
				</div>
				<div class="order-1 flex justify-end lg:order-2" in:fly={{ y: 50, duration: 1000 }}>
					<div class="relative lg:w-[90%] 2xl:w-[80%]">
						<div class="bg-base-300 aspect-square overflow-hidden rounded-lg">
							<img
								src=""
								alt="Portfolio Video"
								class="h-full w-full object-cover"
							/>
						</div>
						<div
							class="border-base-content/5 absolute -right-4 -bottom-4 h-full w-full rounded-lg border-4"
						></div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Services Section -->
	<section class="py-20">
		<div class="container mx-auto px-4">
			<div class="mb-12 text-center">
				<h2 class="text-4xl font-bold" in:fade>Our Services</h2>
				<p class="text-base-content/70 mt-4">
					Comprehensive visual solutions to drive your business forward
				</p>
			</div>
			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each services as service, i}
					<div
						class="card bg-base-200 h-full shadow-xl transition-all hover:-translate-y-2 hover:shadow-2xl"
						in:fly={{ y: 50, duration: 1000, delay: i * 200 }}
					>
						<div class="card-body">
							<div class="flex items-center gap-4">
								<div class="bg-primary/10 rounded-full p-3">
									<svelte:component this={service.icon} class="text-primary h-6 w-6" />
								</div>
								<h3 class="card-title">{service.title}</h3>
							</div>
							<p class="text-base-content/70 mt-4">{service.description}</p>
							<div class="card-actions mt-4 justify-end">
								<a href="#top" class="link link-primary flex items-center">
									Learn more <ChevronRight class="ml-1 h-4 w-4" />
								</a>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Testimonials Section -->
	<section class="bg-base-200 py-20">
		<div class="container mx-auto px-4">
			<h2 class="mb-12 text-center text-4xl font-bold" in:fade>Client Testimonials</h2>
			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each testimonials as testimonial, i}
					<div
						class="card bg-base-100 shadow-xl"
						in:fly={{ y: 50, duration: 1000, delay: i * 200 }}
					>
						<div class="card-body">
							<div class="flex items-center gap-4">
								<div class="avatar">
									<div class="w-16 rounded-full">
										<img src={testimonial.image} alt={testimonial.name} />
									</div>
								</div>
								<div>
									<h3 class="font-bold">{testimonial.name}</h3>
									<p class="text-base-content/70 text-sm">{testimonial.role}</p>
								</div>
							</div>
							<p class="text-base-content/80 mt-4">"{testimonial.content}"</p>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Contact Section -->
	<section class="py-20">
		<div class="container mx-auto px-4">
			<div class="card bg-base-200 mx-auto max-w-3xl shadow-xl" in:fade={{ duration: 1000 }}>
				<div class="card-body">
					<h2 class="mb-8 text-center text-4xl font-bold">Get In Touch</h2>
					<form class="space-y-6">
						<div class="grid gap-6 md:grid-cols-2">
							<div class="form-control w-full">
								<label class="label" for="name">
									<span class="label-text">Name</span>
								</label>
								<input
									type="text"
									id="name"
									placeholder="Your name"
									class="input input-bordered w-full"
								/>
							</div>
							<div class="form-control w-full">
								<label class="label" for="email">
									<span class="label-text">Email</span>
								</label>
								<input
									type="email"
									id="email"
									placeholder="Your email"
									class="input input-bordered w-full"
								/>
							</div>
						</div>
						<div class="form-control">
							<label class="label" for="message">
								<span class="label-text">Message</span>
							</label>
							<textarea
								id="message"
								class="textarea textarea-bordered h-32"
								placeholder="How can we help?"
							></textarea>
						</div>
						<button class="btn btn-primary w-full">Send Message</button>
					</form>
				</div>
			</div>
		</div>
	</section>
</div>
