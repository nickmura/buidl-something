<script lang="ts">
	import {
		accountChainId,
		connected,
		connectMetamask,
		connectWalletConnect,
		disconnect,
		walletAddress
	} from '$lib/stores/provider';
	import { balanceOnBlock } from '$lib/stores/state';
	import { formatEther } from 'ethers/lib/utils';
	import Auction from '$lib/components/Auction.svelte'
	import Buyer from '$lib/components/Buyer.svelte'
	import Seller from '$lib/components/Seller.svelte';
</script>

<main class="flex flex-col p-10 w-screen h-screen items-center gap-5 font-serif">
	<h1 class="text-5xl text-black font-bold">buidl-something</h1>

	<section class="flex flex-row p-10 items-start gap-5 border-2 rounded-xl">
		
		<h2 class="text-xl text-black font-semibold">$connected: {$connected}</h2>
	
	
		<button
			on:click={connectMetamask}
			class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200"
			>Connect via MetaMask</button
		>
		<button
			on:click={connectWalletConnect}
			class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200"
			>Connect via WalletConnect</button
		>
		<button
			on:click={disconnect}
			class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200"
			>Disconnect</button
		>
	</section>
	


	<Auction></Auction>




</main>
