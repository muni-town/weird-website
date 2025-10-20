<script>
	import GroupConnectedIllustration from "$lib/components/GroupConnectedIllustration.svelte";
	import GroupConnectedIllustrationVertical from "$lib/components/GroupConnectedIllustrationVertical.svelte";
</script>

<div class="ellipse-layer">
	<figure class="cloud-left">
		<img alt="cloud" src="cloud.png" />
	</figure>
	<figure class="pigeon">
		<img alt="Pigeon Cartoon" src="pigeon.png" />
	</figure>
	<div class="section-wrapper">
		<div class="content-container">
			<article class="article-content">
				<h3 class="article-title">Bluesky-connected</h3>
				<p class="article-text">
					Roomy is optionally connected with the Bluesky network of 30M people.
				</p>
			</article>
		</div>
		<div class="illustration-desktop">
			<GroupConnectedIllustration />
		</div>
		<div class="illustration-mobile">
			<GroupConnectedIllustrationVertical />
		</div>
	</div>
	<figure class="butterfly">
		<img alt="Butterfly Cartoon" src="bluesky.png" />
	</figure>
	<figure class="cloud-right">
		<img alt="cloud" src="cloud.png" />
	</figure>
</div>

<style>
	.ellipse-layer {
		position: relative;
		padding-block: 8rem;
		width: 100vw;
		color: white;
		background: linear-gradient(to bottom, var(--blue) 0%, var(--p1) 100%);
		max-width: 100%;
		overflow-x: clip;
	}

	.cloud-left,
	.pigeon,
	.butterfly,
	.cloud-right {
		position: absolute;
		top: 10%;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 9999px;
		height: 12.8rem;
		width: 12.8rem;
	}

	.cloud-left {
		left: -1%;
		z-index: 5;
	}

	.pigeon {
		left: 8%;
		z-index: 10;
	}

	.butterfly {
		right: 8%;
		z-index: 10;
	}

	.cloud-right {
		right: -1%;
		z-index: 5;
		transform: scaleX(-1);
	}

	.section-wrapper {
		margin-bottom: 4rem;
		text-align: center;
	}

	.content-container {
		padding-top: 16rem;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 4rem;
	}

	.article-content {
		margin-top: 16rem;
	}

	.article-title {
		margin-bottom: 1.25rem;
		font-size: 3em;
		font-weight: 700;
	}

	.article-text {
		margin-bottom: 2.5em;
		font-size: 1.6rem;
		opacity: 0.9;
	}

	.illustration-desktop {
		display: none;
		align-items: center;
		justify-content: center;
		gap: 1.25rem;
	}

	.illustration-mobile {
		margin-left: auto;
		margin-right: auto;
		display: flex;
		width: 350px;
		align-items: center;
		justify-content: center;
		gap: 1.25rem;
	}
	/* Tablet and up (md: 768px) */
	@media (min-width: 768px) {
		.illustration-mobile {
			width: 400px;
		}
	}

	/* Desktop (lg: 1024px) */
	@media (min-width: 1024px) {
		.cloud-left,
		.pigeon,
		.butterfly,
		.cloud-right {
			height: 20rem;
			width: 20rem;
		}

		.content-container {
			padding-top: 40em;
		}

		.article-content {
			margin-top: 0;
		}

		.illustration-desktop {
			display: flex;
		}

		.illustration-mobile {
			display: none;
		}
	}
</style>
