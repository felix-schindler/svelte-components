<div>
	<header>
		<h1>Welcome to Nimiq Components for Svelte(Kit)</h1>
	</header>
	<main>
		<slot />
	</main>
	<footer></footer>
</div>

<style>
	div {
		display: grid;
		grid-template-rows: auto 1fr auto;
	}

	header, main, footer {
		padding: 1em;
	}
</style>
