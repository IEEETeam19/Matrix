<script>

    import {array} from "../stores/data.js"
    import {OutputArr, flag} from "../stores/outputData.js"
    
    var nums;
    var sym;
    var fc = false;
    export const outArr = [];
    
    const option1 = ()=>{
    let outArr = [];
    let matrixOrder = 10;

    function createUnitMatrix() {
        outArr = [];
        for (let i = 0; i < matrixOrder; i++) {
            outArr[i] = [];
            for (let j = 0; j < matrixOrder; j++) {
                if (i === j) {
                    outArr[i][j] =  1 ;
                } else {
                    outArr[i][j] =  0 ;
                }
            }
        }
    }
    createUnitMatrix();
    OutputArr.set(outArr);
    flag.set(1);
    }

    const option2 = ()=>{
    let outArr = [];
    let matrixOrder = nums;
    let seperator = sym;

    function createUnitMatrix() {
        outArr = [];
        for (let i = 0; i < matrixOrder; i++) {
            outArr[i] = [];
            for (let j = 0; j < matrixOrder; j++) {
                if (i === j) {
                    outArr[i][j] =  1 ;
                } else {
                    outArr[i][j] =  0 ;
                }
                outArr[i][j] = outArr[i][j] + seperator;
            }
        }
    }
    createUnitMatrix();
    OutputArr.set(outArr);
    flag.set(1);

    /*let matrix = [];
let matrixOrder = nums;
let separator = sym;

function createUnitMatrix() {
    let outArr = [];
    for (let i = 0; i < matrixOrder; i++) {
        outArr[i] = [];
        for (let j = 0; j < matrixOrder; j++) {
            if (i === j) {
                outArr[i][j] = 1;
            } else {
                outArr[i][j] = 0;
            }
            outArr[i][j] = outArr[i][j] + separator;
        }
    }
}
    createUnitMatrix();
    OutputArr.set(outArr);
    flag.set(1);*/
    
    }

    /*const pickMore = ()=> {
        
        outArr = [];

        for(var i=0; i<nums; i++)
        {
            var ind = Math.floor(Math.random() * $array.length);    //0,1,2,3 => 1
            outArr = [...outArr, $array[ind]];
        }

        console.log("More elements: "+outArr);
        OutputArr.set(outArr);
        flag.set(1);
    }*/
</script>

<main>
    <div class="bg-teal-700 text-white w-96 px-1" style="height: 420px;">
        <p class="text-center font-bold">Generate A Unit Matrix</p>
        <br>
        <p class="text-justify text-xs">
            A unit matrix is a diagonal matrix where all the diagonal elements are equal to 1 
            and all other elements are 0. The product of any square matrix by the identity matrix 
            is equal to the matrix itself. The symbol n in this notation is equal to the 
            order of the square matrix of dimension n×n. For example, I5 is a 5×5 identity matrix. 
            In this tool, you can specify the order of the matrix (the value of "n").</p>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option1}>
                10th order unit matrix
            </button>
        </div>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option2}>
                Non standard unit matrix
            </button>
        </div>

        <!--<div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={pickMore}>
                Pick more numbers than there are
            </button>
        </div>-->

        <hr class="m-2">

        <h4 class="text-sm">Required options</h4>
        <p class="text-xs">This is an online browser-based program for generating unit matrices
        </p>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-52 rounded text-sm" placeholder="enter size of 'n' for unit matrix" bind:value={nums}>
        </div>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-52 rounded text-sm" placeholder="enter symbol seperator for elements" bind:value={sym}>
        </div>

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