<script>
	import CloseButton from './sub/CloseButton.svelte';

	/**
	 * Is the BottomOverlay currently shown or not?
	 */
	export let visible = true;
	/**
	 * Should the BottomOverlay be closed manually?
	 */
	export let hasCloseButton = false;
	/**
	 * How long should the BottomOverlay be shown
	 */
	export let duration = 5123;
	$: duration = hasCloseButton && duration == 5123 ? 10000 : 5000;

	// If is visible and doesn't have a close
	// button, discard BottomOverlay automatically
	$: if (visible && !hasCloseButton) {
		setTimeout(() => visible = false, duration);
	}
</script>

{#if visible}
	<div class={"bottom-overlay" + (hasCloseButton ? " has-close-button" : "")}>
		<slot />
		{#if hasCloseButton}
		<CloseButton bind:visible />
		<!-- TODO: Show time until it's closed
		{:else}
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

		color: var(--white);
		background: var(--blue);
	}

	.bottom-overlay :global(.close-button) {
		position: absolute;
		top: 1.4rem;
		right: 1.4rem;
	}

	@media screen and (prefers-color-scheme: dark) {
		.bottom-overlay {
			color: var(--blue);
			background: var(--white);
		}
	}

	.has-close-button {
		padding-right: 6.5rem;
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

		.bottom-overlay :global(.close-button) {
			top: 2rem;
			right: 2rem;
		}

		.has-close-button {
			padding-right: 7rem;
		}
	}
</style>
