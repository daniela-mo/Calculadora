<template>
  <div>
    <div class="container">
      <div class="container__calc">
        <div class="container__calc__result">
          <div class="container__calc__result__display">
            <p>{{ valorCorrente || "" }}</p>
          </div>
        </div>
        <div class="container__calc__keyboard">
          <button v-on:click="clear" class="container__calc__keyboard__c">
            C
          </button>
          <button v-on:click="ponto" class="container__calc__keyboard__ponto">
            .
          </button>
          <button
            v-on:click="porcentagem"
            class="container__calc__keyboard__percent"
          >
            %
          </button>
          <button v-on:click="divisao" class="container__calc__keyboard__divis">
            &#247;
          </button>
          <button
            v-on:click="juntarNum('7')"
            class="container__calc__keyboard__number"
          >
            7
          </button>
          <button
            v-on:click="juntarNum('8')"
            class="container__calc__keyboard__number"
          >
            8
          </button>
          <button
            v-on:click="juntarNum('9')"
            class="container__calc__keyboard__number"
          >
            9
          </button>
          <button
            v-on:click="multiplicar"
            class="container__calc__keyboard__multip"
          >
            &times;
          </button>
          <button
            v-on:click="juntarNum('4')"
            class="container__calc__keyboard__number"
          >
            4
          </button>
          <button
            v-on:click="juntarNum('5')"
            class="container__calc__keyboard__number"
          >
            5
          </button>
          <button
            v-on:click="juntarNum('6')"
            class="container__calc__keyboard__number"
          >
            6
          </button>
          <button
            v-on:click="subtracao"
            class="container__calc__keyboard__subtr"
          >
            -
          </button>
          <button
            v-on:click="juntarNum('1')"
            class="container__calc__keyboard__number"
          >
            1
          </button>
          <button
            v-on:click="juntarNum('2')"
            class="container__calc__keyboard__number"
          >
            2
          </button>
          <button
            v-on:click="juntarNum('3')"
            class="container__calc__keyboard__number"
          >
            3
          </button>
          <button v-on:click="adicao" class="container__calc__keyboard__adic">
            +
          </button>
          <button class="container__calc__keyboard__empty" id="empty"></button>
          <button
            v-on:click="juntarNum('0')"
            class="container__calc__keyboard__number"
          >
            0
          </button>
          <button class="container__calc__keyboard__empty" id="empty"></button>
          <button
            v-on:click="resultado"
            class="container__calc__keyboard__resultado"
          >
            =
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.container {
  width: 100%;
  &__calc {
    width: 320px;
    height: 520px;
    background-color: #e1e4e6;
    margin: 0 auto;
    border-radius: 7px;
    box-shadow: 0 8px 10px 0 rgba(0, 0, 0, 0.2);
    &__result {
      height: 120px;
      border: #eef0f1 solid 3px;
      &__display {
        text-align: center;
        height: 20px;
        margin: 0 auto;
        padding-top: 20px;
        font-size: 20px;
        background: #eef0f1;
      }
    }
    &__keyboard {
      height: 400px;
      &__c {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 15px;
        color: rgba(105, 97, 97, 0.705);
        cursor: pointer;
        background: #eef0f1;
      }
      &__ponto {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 25px;
        color: rgba(105, 97, 97, 0.705);
        cursor: pointer;
        background: #eef0f1;
      }
      &__percent {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: 600;
        font-size: 15px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: #cde9b7;
      }
      &__divis {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 20px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: #aacbf6;
      }
      &__multip {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        cursor: pointer;
        font-size: 20px;
        color: rgba(105, 97, 97, 0.705);
        background: #ffdc9a;
      }
      &__subtr {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 25px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: rgb(212, 197, 228);
      }
      &__adic {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 20px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: #d4fbd4;
      }
      &__resultado {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 20px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: rgb(255, 174, 224);
      }

      &__number {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 15px;
        cursor: pointer;
        color: rgba(105, 97, 97, 0.705);
        background: #eaedef;
      }
      &__empty {
        width: 50px;
        border: none;
        height: 50px;
        margin: 15px;
        float: left;
        border-radius: 50px;
        font-weight: bold;
        font-size: 15px;
        background: none;
      }
    }
  }
}
</style>

<script>
import Calculator from "../views/Calculator";
export default {
  Calculator,

  data() {
    // funcao
    return {
      //variaveis
      valorCorrente: "",
      valorAnterior: null,
      valor: null,
      valorClicado: false,
    };
  },

  methods: {
    //Metodo responsável por limpar o display da calculadora
    clear() {
      this.valorCorrente = " ";
    },
    //Método de realizar a porcentagem
    porcentagem() {
      this.valorCorrente = `${parseFloat(this.valorCorrente) / 100}`;
    },
    //responsável por juntar os numeros no display da calculadora
    juntarNum(numero) {
      if (this.valorClicado) {
        this.valorCorrente = "";
        this.valorClicado = false;
      }
      this.valorCorrente = `${this.valorCorrente}${numero}`;
    },
    //metodo responsável por adicionar o ponto no display
    ponto() {
      if (this.valorCorrente.indexOf(".") === -1) {
        this.juntarNum(".");
      }
    },
    setarValor() {
      this.valorAnterior = this.valorCorrente;
      this.valorClicado = true;
    },
    //metodo responsavel por realizar a multiplicacao
    multiplicar() {
      this.valor = (num1, num2) => num1 * num2;
      this.setarValor(); // o setarValor grava o numero clicado primeiro, para que a operação seja realizada
    },
    //metodo responsavel por realizar a adicão
    adicao() {
      this.valor = (num1, num2) => num1 + num2;
      this.setarValor();
    },
    //metodo responsavel por realizar a subtração
    subtracao() {
      this.valor = (num1, num2) => num1 - num2;
      this.setarValor();
    },
    //metodo responsavel por realizar a multiplicacão
    divisao() {
      this.valor = (num1, num2) => num1 / num2;
      this.setarValor();
    },

    //metodo responsavel por apresentar o resultado das operações
    resultado() {
      this.valorCorrente = `${this.valor(
        parseFloat(this.valorAnterior),
        parseFloat(this.valorCorrente)
      )}`;
      this.valorAnterior = null;
    },
  },
};

//   data (getHistory){
//    return document.getElementById("history-value").innerText;
//  },
//   data(printHistory){
//    document.ElementById("history-value").innerText = num;
//  },
//  data (getOutput){
//    return document.getElementById("output-value").innerText;
//  },
// data (printOutput){
//   if(num == ""){
//    document.getElementById("output-value").innerText = num;
//  }else{
//    document.getElementById("output-value").innerText = getFormattedNumber(num);
//  }
// },
// data (getFormattedNumber){
//   if(num == "-") {
//    return "";
//  }
// n = Number(num);
// value = n.toLocaleString("en");
// return value;
// },
// reverseNumberFormat(num){
//   return Number(num.replace(/,/g, ""));
// },
// operator=document.getElementByClassName("operator"),
// for( i = 0 i < operator.length i++) {
// operator[i].addEventListner("click", function (){
//   if(this.id == "clear"){
//     printHistory("");
//     printOutput("");
//   }else if(this.id =="backspace"){
//     output =reverseNumberFormat(getOutput()).toString();
//     if(output){
//       //if output has a value
//     output = output.substr(0, output.length - 1);
//     printOutput(output);
//     }
//   }
//   else{
//     output = getOutput();
//     history = getHistory();
//     if(output == "" && history != "") {
//       if(isNaN(history[history.length - 1])){
//         history = history.substr(0, history.length - 1);
//       }
//     }
//     if(output != "" || history != ""){
//       output = output == "" ? output : reverseNumberFormat(output);
//       history = history + output;
//       if (this.id == "="){
//         result = eval(history);
//         printOutput(result);
//         printHistory("");
//       }else{
//         history = history + this.id;
//         printHistory(history);
//         printOutput("");
//       }
//     }
//   }
// });
// }

// number = document.getElementByClassName("number");
// for (i = 0, < number.length, i++) {
//   number [i].addEventListner("click", function(){
//     output = reverseNumberFormat(getOutput());
//     if (output != NaN){
//       //if output is a number
//       output = output + this.id;
//       printOutput(output);
//     }
//   });
// }
</script>
