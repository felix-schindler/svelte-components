<script>
	export let shown;
</script>

<button class="close-button nq-button-s" on:click={() => shown = false}>
	<svg class="bi bi-x nq-icon" xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
		<path d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/>
	</svg>
</button>

<style scoped>
	button {
		font-size: 3rem;
		padding: 0;
		background: none !important;
		height: 3rem;
	}

	button::before {
		border-radius: 50%;
	}

	button .nq-icon {
		opacity: 0.2;
		transition: opacity 0.3s var(--nimiq-ease);
	}

	button:hover .nq-icon,
	button:active .nq-icon,
	button:focus .nq-icon {
		opacity: 0.4;
	}

	button.top-right {
		position: absolute;
		top: 2rem;
		right: 2rem;
	}
</style>
