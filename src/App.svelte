<script lang="ts">
	let name: string | undefined = undefined;

	import Verida from '@verida/datastore';
	let receiver;
	let app;
	let appConfig;
	let appName = "..";

	const DID = '<paste your DID here>';
	const SIGNATURE = '<paste your signature here>';
	async function createApp(){
	
		// Verida.setConfig({
		// 	appName: appName
		// });
	
		app = new Verida({
			did: DID,
			signature: SIGNATURE,
			appName: appName,
		});
		await app.connect(true);
		name = app.user.did;
		appConfig = await app.user.getAppConfig();
	}
	
</script>

<main>
	<button on:click={createApp}>Login</button>
	{#if name !== undefined}
	<p>Hello {name}</p>

	{JSON.stringify(appConfig)}
	{/if}
</main>

<style lang="scss">
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;

		h1 {
			color: #ff3e00;
			text-transform: uppercase;
			font-size: 4em;
			font-weight: 100;
		}

		@media (min-width: 640px) {
			max-width: none;
		}
	}
</style>
