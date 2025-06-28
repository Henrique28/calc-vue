<script setup>

import { reactive, computed } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
	num1: 0,
	num2: 0,
	operador: '+'
});

const resultadoOperacao = computed(() => {
	const n1 = parseFloat(estado.num1);
	const n2 = parseFloat(estado.num2);

	let resultado;

	switch (estado.operador) {
		case '+': 
			resultado = n1 + n2;
			break;
		case '-': 
			resultado = n1 - n2;
			break;
		case '*': 
			resultado = n1 * n2;
			break;
		case '/': 
			if (n2 === 0) return 'Erro: divisão por zero';
			resultado = n1 / n2;
			break;
		default: 
			return 'Operação Inválida';
			break;
	}

	return isNaN(resultado) ? '' : parseFloat(resultado.toFixed(2));
});

</script>

<template>
	<div class="container">
		<Cabecalho/>
		<Formulario :campo1="e => estado.num1 = e.target.value" :campo2="e => estado.num2 = e.target.value" :operacao="e => estado.operador = e.target.value"/>
		<Resultado :resultado="resultadoOperacao"/>
	</div>
</template>