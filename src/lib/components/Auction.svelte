<script lang='ts'>

    let create = false;

    function toggleCreate (){
        create = !create;
    }

    let auction = {
        name: '',
        description: '',
        startingBid: '',
        duration: '', 
        currentBid: '',
    }   
    

</script>


{#if !create}   
    <button on:click={toggleCreate} class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200">
        Create New Auction
    </button> 
{:else}

<div class="border-10  p-10 rounded-xl gap-6 flex flex-row ">
   
    
      
    <div class="flex flex-col gap-6">
    <input bind:value={auction.name} class="inputs" placeholder="Name Your Auction">
    <input bind:value={auction.description} class="inputs" placeholder="Description">
    <input bind:value={auction.startingBid} type="number" class="inputs" placeholder="Starting Bid">
    <input bind:value={auction.duration} type="number" class="inputs" placeholder="Duration">

    <button on:click={toggleCreate} class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200">
        Create
    </button> 
    </div>

    <div class="w-80 border-black border-2 rounded-xl flex flex-col">
        <p class="self-center">Preview</p>
    
    
    
    
    
    </div>
</div>
{/if}


    
<style> 

.inputs{
    @apply rounded-xl border-black border-2  p-2 
}

</style>
