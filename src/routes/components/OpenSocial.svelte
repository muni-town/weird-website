<script>
	import GroupConnectedIllustration from '$lib/components/GroupConnectedIllustration.svelte';
	import GroupConnectedIllustrationVertical from '$lib/components/GroupConnectedIllustrationVertical.svelte';
</script>

<div class="ellipse-layer relative min-h-screen w-screen">
	<figure
		class="absolute top-[10%] left-[-1%] z-5 flex h-32 w-32 items-center justify-center rounded-full lg:h-80 lg:w-80"
	>
		<img alt="Left Mountain" src="/images/mountain.png" />
	</figure>
	<figure
		class="absolute top-[10%] left-[8%] z-10 flex h-32 w-32 items-center justify-center rounded-full lg:h-80 lg:w-80"
	>
		<img alt="Pigeon Cartoon" src="/images/pigeon.png" />
	</figure>
	<div class="section-wrapper mb-16 text-center">
		<div class="flex items-center justify-center gap-16 lg:mt-64">
			<article class="mt-64 lg:mt-0">
				<h3 class="mb-5 text-3xl font-bold">Bluesky-connected</h3>
				<p class="mb-10 text-base opacity-90">
					Roomy is optionally connected with the Bluesky network of 30M people.
				</p>
			</article>
		</div>
		<div class="hidden items-center justify-center gap-5 lg:flex">
			<GroupConnectedIllustration />
		</div>
		<div
			class="mx-auto flex w-[350px] items-center justify-center gap-5 md:w-[400px] lg:hidden"
		>
			<GroupConnectedIllustrationVertical />
		</div>
	</div>
	<figure
		class="absolute top-[10%] right-[8%] z-10 flex h-32 w-32 items-center justify-center rounded-full lg:h-80 lg:w-80"
	>
		<img alt="Butterfly Cartoon" src="/images/bluesky.png" />
	</figure>
	<figure
		class="absolute top-[10%] right-[-1%] z-5 flex h-32 w-32 scale-x-[-1] items-center justify-center rounded-full lg:h-80 lg:w-80"
	>
		<img alt="Left Mountain" src="/images/mountain.png" />
	</figure>
</div>
