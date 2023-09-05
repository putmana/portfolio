<script lang="ts">
	export let header: string | null = null
	export let buttonLink: string | null = null
	export let buttonLabel: string | null = null
	export let size: string = "1"
</script>

<div class="card" style="flex: {size}">
	{#if header != null}
		<div class="header">
			{header}
		</div>
	{/if}

	<div class="body">
		<slot />
	</div>

	{#if buttonLink !== null && buttonLabel !== null}
		<div class="footer">
			<a class="btn-primary" href={buttonLink}>
				{buttonLabel}
			</a>
		</div>
	{/if}
</div>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	.card {
		flex: 1;
		color: lib.$color-accent-a;
		background-color: lib.$color-bg-b;
		padding: 60px;
		min-width: 200px;

		.header {
			display: flex;
			font-size: 30pt;
			font-weight: 700;
			letter-spacing: -2px;
		}
		.body {
			display: flex;
			flex-direction: column;
			margin-top: 20px;
			margin-left: 8px;
			padding-left: 30px;
			font-size: 14pt;
			font-weight: 500;
			border-left: 3px dotted lib.$color-accent-a;
		}
		.footer {
			display: flex;
			margin-top: 40px;
			margin-left: 6px;
		}
	}
	@media (max-width: lib.$large) {
		.card {
			flex: 1;
			padding: 30px;
			.header {
				justify-content: center;
				font-size: 30pt;
				letter-spacing: -2px;
			}
			.body {
				font-size: 12pt;
				margin-left: 0px;
			}
			.footer {
				justify-content: center;
				margin-left: 0px;
			}
		}
	}
</style>
