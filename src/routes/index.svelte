<script>
	import BottomOverlay from "../Components/BottomOverlay.svelte";
	import HexSpinner from "../Loading/HexSpinner.svelte";
	import Spinner from "../Loading/Spinner.svelte";

	let visible = true;
</script>

<div class="cards">
	<div class="card">
		<div class="card-header">
			<h1>BottomOverlay</h1>
		</div>
		<div class="card-content">
			<button class="orange" type="button" on:click={() => visible = true}>Show BottomOverlay</button>
			<BottomOverlay bind:visible hasCloseButton={true}>
				<div>It's nice to see you!</div>
			</BottomOverlay>
		</div>
	</div>
	<div class="card">
		<div class="card-header">
			<h1>Loading</h1>
		</div>
		<div class="card-content">
			<HexSpinner />
			<Spinner />
		</div>
	</div>
</div>

<style>
	.card-content {
		text-align: center;
	}
</style>
