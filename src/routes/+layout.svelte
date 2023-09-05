<script lang="ts">
	import Navbar from "$lib/components/navbar.svelte"
	import "../app.scss"
</script>

<Navbar></Navbar>
<section class="content">
	<slot />
</section>
<section class="footer">
	<div class="logo">
		PTMN<span class="darken">.</span>
	</div>
	<div class="text">Email: adam@ptmn.io</div>
	<div class="text">Copyright &copy 2023 Adam Putman. All rights reserved.</div>
</section>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	.content {
		min-height: calc(100vh - 60px);
	}
	.footer {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 20px;
		background-color: lib.$color-accent-a;
		.logo {
			color: lib.$color-bg-b;
			font-size: 14pt;
			font-weight: 800;
			padding: 10px;
			.darken {
				color: lib.$color-bg-c;
			}
		}
		.text {
			color: lib.$color-bg-b;
			font-size: 10pt;
			font-weight: 300;
			padding: 5px;
		}
	}
</style>
