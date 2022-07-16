<script>
	import CloseButton from './sub/CloseButton.svelte';

	export let visible = true;
	export let hasCloseButton = false;

	if (!hasCloseButton) {
		setTimeout(() => {
			visible = false;
			console.log("Called!");
		}, 5000);
	}
</script>

{#if visible}
	<div class={"bottom-overlay" + (hasCloseButton ? "hasCloseButton" : "")}>
		<slot />
		{#if hasCloseButton}
			<CloseButton class="close-button" bind:visible />
		<!-- {:else}
			<Timer duration={5} /> -->
		{/if}
	</div>
{/if}

<style>
	.bottom-overlay {
		position: fixed;
		left: 50%;
		bottom: 2rem;
		max-width: 110rem;
		padding: 1.5rem 2rem 1.75rem 2rem;
		border-radius: 1.25rem;
		box-shadow: 0 0 2.5rem rgba(0, 0, 0, 0.111158);
		font-size: 2rem;
		line-height: 1.3;
		transform: translateX(-50%);

		color: var(--white) !important;
		background: var(--blue);
	}

	@media screen and (prefers-color-scheme: dark) {
		.bottom-overlay {
			background: var(--white);
			color: var(--blue);
		}
	}

	.has-close-button {
		padding-right: 6.5rem;
	}

	.close-button {
		position: absolute;
		top: 1.5rem;
		right: 1.5rem;
	}

	@media (max-width: 912px) {
		.bottom-overlay {
			bottom: 1.5rem;
			width: calc(100% - 3rem);
		}
	}

	@media (max-width: 450px) {
		.bottom-overlay {
			left: 0;
			bottom: 0;
			width: 100%;
			padding: 2.5rem;
			border-bottom-left-radius: 0;
			border-bottom-right-radius: 0;
			transform: none;
		}

		.has-close-button {
			padding-right: 7rem;
		}

		.close-button {
			top: 2rem;
			right: 2rem;
		}
	}
</style>
