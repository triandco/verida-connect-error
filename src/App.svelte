<script lang="ts">
	let name: string = 'world';

	import Verida from '@verida/datastore';

	async function createApp(){
		// Fetch the users web3Provider and address
		const web3Provider = await Verida.Helpers.wallet.connectWeb3('ethr');
		const address = await web3Provider.getAddress('ethr');
	
		Verida.setConfig({
			appName: 'Your Application Name'
		});
	
		let app = new Verida({
				chain: 'ethr',
				address: address,
				web3Provider: web3Provider
		});
		await app.connect(true);
		name = app.user.did;
	}

</script>

<main>
	<h1>Hello {name}!</h1>
	<button on:click={createApp}>Click</button>
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
