<script>

    import {array} from "../stores/data.js"
    import {OutputArr, flag} from "../stores/outputData.js"
    
    var nums, row, col, snum, lnum;
    var fc = false;
    export const outArr = [];
    
    const option1 = ()=>{

    let outArr = [];
    let rows = 6;
    let columns = 6;
    let min = snum;
    let max = lnum;

    function createMatrix() {
        outArr = [];
        for (let i = 0; i < rows; i++) {
            outArr[i] = [];
            for (let j = 0; j < columns; j++) {
                outArr[i][j] = Math.floor(Math.random() * (max - min + 1) + min);
            }
        }
    }
    createMatrix();
    OutputArr.set(outArr);
    flag.set(1);

    }

    const option2 = ()=>{
     
    let outArr = [];
    let rows = row;
    let columns = col;
    let min = snum;
    let max = lnum;
    outArr = new Array(rows);
        for (let i = 0; i < rows; i++) {
            outArr[i] = new Array(columns);
            for (let j = 0; j < columns; j++) {
                if(i === j) {
                    outArr[i][j] = Math.floor(Math.random() * (max - min + 1) + min);
                } else {
                    outArr[i][j] = 0;
                }
            }
        }

        OutputArr.set(outArr);
        flag.set(1);
    }

    const option3 = ()=> {
        
    let outArr = [];
    let rows = row;
    let min = snum;
    let max = lnum;
    outArr = new Array(rows);
        for (let i = 0; i < rows; i++) {
            outArr[i] = new Array(rows);
            for (let j = 0; j < rows; j++) {
                if (i <= j) {
                    outArr[i][j] = Math.floor(Math.random() * (max - min + 1) + min);
                } else {
                    outArr[i][j] = outArr[j][i];
                }
            }
        }
        OutputArr.set(outArr);
        flag.set(1);
    }
</script>

<main>
    <div class="bg-teal-700 text-white w-96 px-1" style="height: 420px;">
        <p class="text-center font-bold">Generate Random Matrices</p>
        <br>
        <p class="text-justify text-xs">
            You can generate random matrices of any size, shape, and form. 
            All you need to do is enter the number of rows and columns in the options 
            above as well as set the lowest and highest possible numeric values for random elements. 
            You can also choose elements to be either integer or decimal numbers with the given precision. 
</p>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option1}>
                Random 6x6 matrix
            </button>
        </div>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option2}>
                Random diagonal matrix
            </button>
        </div>

        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option3}>
                Random diagonal matrix
            </button>
        </div>

        <hr class="m-2">

        <h4 class="text-sm">Required options</h4>
        <p class="text-xs">This is an online browser-based program for generating random matrices
        </p>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-28 rounded text-sm" placeholder="number of rows" bind:value={row}>
        </div>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-32 rounded text-sm" placeholder="number of columns" bind:value={col}>
        </div>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-40 rounded text-sm" placeholder="smallest random number" bind:value={snum}>
        </div>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-40 rounded text-sm" placeholder="largest random number" bind:value={lnum}>
        </div>

        <!--<div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-52 rounded text-sm" placeholder="column delimiter of output matrix" bind:value={nums}>
        </div>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-52 rounded text-sm" placeholder="row delimiter of output matrix" bind:value={nums}>
        </div>-->
        <!-- <input type="text" class="bg-teal-900 m-2 h-5 rounded text-sm" placeholder="\n">
        <p class="text-xs">Input numbers are seperated by this symbol(new line)</p> -->
        
        <!-- <label for="op4" class="text-white text-xs font-bold">
            <input type="checkbox" name="oprI" id="" bind:checked={fc}>
                {#if fc}
                    {sampleWithRepetitions}
                {/if}
                With Repetions
        </label> -->

        <!-- <p class="text-xs">Allowing choosing the same number for several time</p> -->

    </div>
</main>
