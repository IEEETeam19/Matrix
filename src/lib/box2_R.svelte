<script>
    import App from "../App.svelte";
    import matrix from "../App.svelte";

    import {array} from "../stores/data.js"
    import {OutputArr, flag} from "../stores/outputData.js"
    
    var nums;
    var fc = false;
    export var outArr = [];
    const option1 = ()=>{

        function findTranspose() {
    for (let i = 0; i < matrix.length; i++) {
      for (let j = 0; j < matrix[i].length; j++) {
        if (!outArr[j]) {
            outArr[j] = [];
        }
        outArr[j][i] = matrix[i][j];
      }
    }
  }
    findTranspose();
        OutputArr.set(outArr);
        flag.set(1);

    }

    const option2 = ()=>{
     
        outArr = [];

        if(nums > $array.length)
        {
            alert(`Array has only ${$array.length} elements, you are trying to get ${nums} elements.`);
            return;
        }
        for(var i=0; outArr.length < nums; i++)
        {
            var ind = Math.floor(Math.random() * $array.length);    //0,1,2,3 => 1
            outArr = [...outArr, $array[ind]];
        }
        
        console.log("selected with rep: "+outArr);
        OutputArr.set(outArr);
        flag.set(1);
    }

    const option3 = ()=> {
        
        outArr = [];

        for(var i=0; i<nums; i++)
        {
            var ind = Math.floor(Math.random() * $array.length);    //0,1,2,3 => 1
            outArr = [...outArr, $array[ind]];
        }

        console.log("More elements: "+outArr);
        OutputArr.set(outArr);
        flag.set(1);
    }
</script>

<main>
    <div class="bg-teal-700 text-white w-96 px-1" style="height: 420px;">
        <p class="text-center font-bold">Calculate Matrix Determinant</p>
        <br>
        <p class="text-justify text-xs">
            This tool supports any NxN matrices and the most effective algorithm for doing it is Gaussian elimination, which is used here.
            It uses elementary matrix operations to transform a matrix into the upper triangular form. 
            By default input matrix's elements are separated by spaces and rows by newlines but you can adjust the delimiters that 
            separate columns and rows in the options above. You can also adjust the accuracy of the calculated 
            determinant by setting the number of digits after the decimal point. </p>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option1}>
                determinant of 3X3 matrix
            </button>
        </div>
        
        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option2}>
                Upper triangular matrix
            </button>
        </div>

        <div class="items-center mx-10">
            <button class="bg-teal-900 w-full text-xs" on:click={option3}>
                Matrix with proportional rows
            </button>
        </div>

        <hr class="m-2">

        <h4 class="text-sm">Required options</h4>
        <p class="text-xs">This is an online browser-based program for calculating determinant of matrices
        </p>

        <div class="content-center m-auto">
            <input type="text" class="bg-teal-900 m-2 h-5 w-56 rounded text-sm" placeholder="number of digits after decimal" bind:value={nums}>
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