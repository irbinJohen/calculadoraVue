<template>
    <div class="font-semibold text-center bg-blue-200 ">
        <h1 >Calculadora vue: irbin johen burciaga aviles  </h1>
    </div>
    <div class=" h-screen bg-blue-600 flex justify-center py-16 ">
        <div class="w-1/3">
            <div class=" p-4 text-right shadow-2*1  rounded-t-k bg-white ">     
                    <p class="font-semibold text-gray-600 h-6 ">{{ getOperation }}</p>
                    <p class=" font-bold text-3*1 text-gray-900 my-2">{{ getResult }}</p>
            </div> 
            <div class="grid  grid-cols-4 grid-rows-5 shadow-2x1 rounded-t-lg bg-white">
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300 col-span-2 hover:bg-blue-500" @click="clickAC()">AC</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="clickDEL()">DEL</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-400 border-blue-300  hover:bg-gray-500" @click="click('/')">/</button>

                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('7')">7</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('8')">8</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('9')">9</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-400 border-blue-300  hover:bg-gray-500" @click="click('*')">*</button>

                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('4')">4</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('5')">5</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('6')">6</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-400 border-blue-300  hover:bg-gray-500" @click="click('-')">-</button>

                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('1')">1</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('2')">2</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('3')">3</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-400 border-blue-300  hover:bg-gray-500" @click="click('+')">+</button>

                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300   col-span-2 hover:bg-blue-500" @click="click('0')">0</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-400 border-blue-300  hover:bg-blue-500" @click="click('.')">.</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-400 border-blue-300  hover:bg-gray-500" @click="clickResult()">=</button>
                
            </div>
        </div>        
    </div>

   

</template>

<script>

export default {

data (){
    return {
        getOperation: '',
        getResult:'0',
    
    }
    },

    methods:{

    clickAC(){
        this.getResult ='0';
    },
    clickDEL(){
        if(this.getResult.length>1){
        this.getResult= this.getResult.substring(0,this.getResult.length-1);
        }else{
            this.getResult ='0';
        }
    },

    
    click (par){
        if(this.getResult=='0'){
        this.getResult=par;
        }else{
            this.getResult+=par;
}    
              },  
    clickResult(){
        let operation=this.getResult;
        this.getOperation = operation;
        this.getResult = eval(operation);
    }          

            }
}
    

  </script>

<style >
button{
    border : 1px solid;
}

</style>
