<script>

  import Box1 from "./lib/box1_R.svelte";
  import Box3 from "./lib/box3_R.svelte";
  import {OutputArr, flag} from "../src/stores/outputData.js";

  /*let matrix = [[]];
  let currentRow = 0;

  function handleEnter(event) {
    if (event.key === "Enter") {
      currentRow++;
      matrix.push([]);
    }
  }

  function handleInput(event) {
    matrix[currentRow].push(event.target.value);
  }*/
  
</script>

<main>

<h2 class="font-bold text-center text-teal-900 text-lg">ONLINE NUMBER TOOLS</h2>
<p class="text-center text-sm m-1"> <span class="bg-black text-teal-400 rounded px-1">Matrix Calculator</span> Choose from the following</p>

<div class="bg-black w-full h-96 my-5">
  <div class="text-white"> 
    </div>
    <div class="flex center-contents justify-evenly">
        <!--<div class="text-teal-700 mx-20 text-center my-4">
            <p class="font-bold">INPUT</p>
            <input type="number" id="input" placeholder="Enter matrix element">
            

            <textarea class="text-white bg-teal-600 w-96 h-72" name="" id="input" cols="30" rows="10" on:keydown={handleEnter}></textarea>
            
            <div>
            <button on:click={handleInput} class="bg-teal-700 text-white rounded border-2 m-1 p-1 hover:bg-teal-900">SUBMIT</button>
            </div>
        </div>-->
        <div class="text-teal-700 mx-20 text-center my-4">
            <p class="font-bold">OUTPUT</p>
            <div class="bg-teal-600 w-96 h-72 text-white" id="Op">
              {#if $flag == 1}
                {#each $OutputArr as ele}
                  <ul>{ele}</ul>
                {/each}
              {/if}
          </div>
        </div>
    </div>
</div>

  <div class="flex content-center mx-3 justify-evenly">
    <Box1/>
    <!--<Box2/>-->
    <Box3/>
  </div>
  <div class="text-center text-teal-800 font-bold">
    END
  </div>
</main>
