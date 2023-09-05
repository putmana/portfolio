<script lang="ts">
	export let header: string
	export let image: string | null = null
	export let buttonLink: string | null = null
	export let buttonLabel: string | null = null
	export let reversed: boolean = false
	export let disabled: boolean = false
	export let alt: string = ""
	export let tag: string | null = null
</script>

<div class="card" class:reversed>
	<div class="info">
		<div class="header">
			<div>
				{header}
			</div>

			{#if tag !== null}
				<div class="tag">
					{tag}
				</div>
			{/if}
		</div>
		<div class="body">
			<slot />
		</div>
		{#if buttonLink !== null && buttonLabel !== null}
			<div class="footer">
				<button
					class="btn-primary"
					on:click={() => {
						window.location.href = buttonLink ?? "#"
					}}
					{disabled}
				>
					{buttonLabel}
				</button>
			</div>
		{/if}
	</div>
	{#if image !== null}
		<div class="image">
			<img src={image} {alt} />
		</div>
	{/if}
</div>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	.card {
		display: flex;
		flex-direction: row;
		flex: 1;
		min-height: 300px;
		color: lib.$color-accent-a;
		border-color: lib.$color-accent-a;
		background-color: lib.$color-bg-b;
		padding: 60px;
		.info {
			flex: 2;
			display: flex;
			flex-direction: column;

			.header {
				display: flex;
				flex-wrap: wrap;
				font-size: 30pt;
				font-weight: 600;
				letter-spacing: -1px;
				align-items: center;
				gap: 15px;

				.tag {
					font-weight: 500;
					text-align: center;
					letter-spacing: 0px;
					font-size: 10pt;
					border: 3px dotted lib.$color-accent-a;
					padding: 8px;
					padding-left: 8px;
					padding-right: 8px;
				}
			}
			.body {
				display: flex;
				flex-direction: column;
				flex-grow: 1;
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
		.image {
			padding-left: 60px;
			display: flex;
			flex: 3;

			img {
				box-shadow: 8px 8px 0px lib.$color-bg-c;
				max-width: 100%;
				max-height: 100%;
				object-fit: cover;
				object-position: left;
			}
		}
		&.reversed {
			flex-direction: row-reverse;
			.image {
				padding-left: 0px;
				padding-right: 60px;
			}
		}
	}
	@media (max-width: lib.$xlarge) {
		.card {
			flex-direction: column-reverse;

			.image {
				padding-left: 0px;
				padding-bottom: 30px;
			}

			&.reversed {
				flex-direction: column-reverse;
				.image {
					padding-right: 0px;
				}
			}
		}
	}
	@media (max-width: lib.$large) {
		.card {
			padding: 0px;
			.info {
				padding: 30px;
				.header {
					flex-direction: column;
					font-size: 20pt;
					justify-content: center;
					.tag {
						margin-top: 10px;
					}
				}
				.body {
					font-size: 12pt;
					margin-left: 0px;
				}
				.footer {
					justify-content: center;
				}
			}
			.image {
				padding-bottom: 0px;
				border-bottom: 3px solid lib.$color-accent-a;
				img {
					box-shadow: none;
				}
			}
		}
	}
</style>
