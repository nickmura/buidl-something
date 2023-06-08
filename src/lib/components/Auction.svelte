<script lang='ts'>

    let create = false;

    function toggleCreate (){
        create = !create;
    }


</script>
    
    
 {#if !create}   
    <button on:click={toggleCreate} class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200">
        Create New Auction
    </button>   
{:else}
    <input id="name" class="border-2 border-black" placeholder="Name Your Auction">
    <input id="startingBid" class="border-2 border-black" placeholder="Starting Bid">
    <input id="description" class="border-2 border-black" placeholder="Description">
    <input id="timeLimit" class="border-2 border-black" placeholder="Description">
{/if}
