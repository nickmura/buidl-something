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
    <button type="button" on:click={toggleCreate} class="relative block w-full rounded-lg border-2 border-dashed border-gray-300 p-12 text-center hover:border-gray-400 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
        <svg class="mx-auto h-12 w-12 text-gray-400" stroke="currentColor" fill="none" viewBox="0 0 48 48" aria-hidden="true">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 14v20c0 4.418 7.163 8 16 8 1.381 0 2.721-.087 4-.252M8 14c0 4.418 7.163 8 16 8s16-3.582 16-8M8 14c0-4.418 7.163-8 16-8s16 3.582 16 8m0 0v14m0-4c0 4.418-7.163 8-16 8S8 28.418 8 24m32 10v6m0 0v6m0-6h6m-6 0h-6" />
        </svg>
        <span class="mt-2 block text-sm font-semibold text-gray-900">Create A New Auction</span>
    </button>
  
{:else}

<div class="border-10  p-10 rounded-xl gap-6 flex flex-row ">
   
    
      
    <div class="flex flex-col gap-6">

    
    <div class="rounded-md px-3 pb-1.5 pt-2.5 shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-indigo-600">
        <label for="name" class="block text-xs font-medium text-gray-900">Name</label>
        <input type="text" bind:value={auction.name} id="name" class="block w-full border-0 p-0 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6" placeholder="Jane Smith">
    </div>

    <div>
        <label  class="block text-sm font-medium leading-6 text-gray-900">Description</label>
        <div class="mt-2">
          <textarea rows="4" bind:value={auction.description} id="description" class="px-2 block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" placeholder="Description"></textarea>
        </div>
      </div>

    

    <div>
        <label class="block text-sm font-medium leading-6 text-gray-900">Starting Bid</label>
        <div class="relative mt-2 rounded-md shadow-sm">
          <div class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3">
            <span class="text-gray-500 sm:text-sm">$</span>
          </div>
          <input type="text" bind:value={auction.startingBid} id="price" class="block w-full rounded-md border-0 py-1.5 pl-7 pr-20 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" placeholder="0.00">
          <div class="absolute inset-y-0 right-0 flex items-center">
            <label for="currency" class="sr-only">Currency</label>
            <select id="currency" name="currency" class="h-full rounded-md border-0 bg-transparent py-0 pl-2 pr-7 text-gray-500 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm">
              <option>USD</option>
              <option>CAD</option>
              
            </select>
          </div>
        </div>
    </div>

    <div>
        <label class="block text-sm font-medium leading-6 text-gray-900">Duration</label>
        <div class="relative mt-2 rounded-md shadow-sm">
          <div class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3">
            <span class="text-gray-500 sm:text-sm"></span>
          </div>
          <input type="text" bind:value={auction.duration} class="block w-full rounded-md border-0 py-1.5 pl-7 pr-20 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" placeholder="0">
          <div class="absolute inset-y-0 right-0 flex items-center">
            <label class="sr-only">Unit</label>
            <select class="h-full rounded-md border-0 bg-transparent py-0 pl-2 pr-7 text-gray-500 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm">
              <option>Hours</option>
              <option>Days</option>
              
            </select>
          </div>
        </div>
    </div>

    <button on:click={toggleCreate} class="p-3 rounded-xl text-xl bg-black text-white font-semibold hover:scale-[1.05] transition transition-200">
        Create
    </button> 
    </div>

    <div class="w-80 border-2 rounded-xl flex flex-col">
        <p class="self-center">Preview</p>
    
    
    
    
    
    </div>
</div>
{/if}


    
<style> 

.inputs{
    @apply rounded-xl border-black border-2  p-2 
}

</style>
