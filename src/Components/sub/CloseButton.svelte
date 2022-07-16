<script>
	export let visible;
</script>

<button class="close-button s inverse" on:click={() => visible = false}>
	<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
		<path d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/>
	</svg>
</button>

<style>
	button {
		font-size: 3rem;
		padding: 0;
		height: 3rem;
	}

	button::before {
		border-radius: 50%;
	}

	button svg {
		opacity: 0.2;
		transition: opacity 0.3s var(--ease);
	}

	button:hover svg,
	button:active svg,
	button:focus svg {
		opacity: 0.4;
	}

	svg {
		height: 3rem;
		width: 3rem;
	}
</style>
