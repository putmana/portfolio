<script lang="ts">
	export let size: string = "1"
</script>

<div class="card" style="flex: {size}">
	<div class="body">
		<slot />
	</div>
</div>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	.card {
		color: lib.$color-bg-a;
		background-color: lib.$color-accent-b;
		padding: 40px;
		padding-top: 20px;
		padding-bottom: 20px;
		.body {
			font-size: 40pt;
			font-weight: 600;
			text-transform: uppercase;
			letter-spacing: -3px;
			text-align: center;
		}
	}
	@media (max-width: lib.$large) {
		.card {
			padding: 20px;
			padding-top: 10px;
			padding-bottom: 10px;
			.body {
				font-size: 20pt;
				letter-spacing: -1px;
			}
		}
	}
</style>
