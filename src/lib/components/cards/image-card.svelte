<script lang="ts">
	export let image: string
	export let caption: string
</script>

<div class="card" style="--hero-img: url({image})"></div>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	.card {
		flex: 1;
		min-width: 300px;
		min-height: 400px;
		background-image: var(--hero-img);
		background-position: top center;
		background-size: cover;
	}
</style>
