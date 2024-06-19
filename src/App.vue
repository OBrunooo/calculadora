<script setup>
import { reactive } from 'vue';
import valores from './components/valores.vue'
import operador from './components/operador.vue'


const conta = reactive ({
  n1: Number,
  n2: Number,
  operacao: "+",
  resultado: 0,
})

conta.n1 = 0;
conta.n2 = 0;

function n1valor (evento) {
  conta.n1 = (evento.target.value)
  conta.n1 = Number(conta.n1)
  resultado()
}

function n2valor (evento) {
  conta.n2 = (evento.target.value);
  conta.n2 = Number(conta.n2)
  resultado()
}

function operacao (evento) {
  conta.operacao = evento.target.value
  resultado()
}


function resultado () {
  if(conta.operacao === "+") {
    conta.resultado = conta.n1 + conta.n2
  }
  if (conta.operacao === "-"){
    conta.resultado = conta.n1 - conta.n2
  }
  if (conta.operacao === "X"){
    conta.resultado = conta.n1 * conta.n2
  }
  if (conta.operacao === "÷"){
    conta.resultado = conta.n1 / conta.n2
  }

}



</script>
<template>
  <div class="container">
    <valores :n1valor="n1valor" :n2valor="n2valor"></valores>
    <div class="operadorResultado">
      <operador :operacao="operacao"</operador>
      <div class="resultado">
        {{ conta.n1 }} {{ conta.operacao }} {{ conta.n2 }} = {{ conta.resultado }}
      </div>
    </div>
  </div>
</template>


<style scoped>
  .container {
    width: 60%;
    margin: 0 auto;
    text-align: center;

    .operadorResultado {
      display: flex;
      justify-content: center;

      .resultado {
        padding-left: 10px;
        font-size: 20px;
      }
    }
  }
</style>
