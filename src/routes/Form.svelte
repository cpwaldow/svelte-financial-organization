<script>
	import Card from './Card.svelte';
	let salario = '';
	let localValue = {
		gastoFixo: '',
		gastoVariavel: '',
		poupar: ''
	};

	function handleInput() {
		const percentValue = (salario, percent) => {
			return (Number(salario.replace(',', '.')) * percent).toFixed(2);
		};

		localValue = {
			gastoFixo: percentValue(salario, 0.7),
			gastoVariavel: percentValue(salario, 0.2),
			poupar: percentValue(salario, 0.1)
		};
		const somatoria = Object.values(localValue).reduce((acc, cur) => {
			acc += Number(cur);

			return acc;
		}, 0);
		salario = '';
	}
</script>

<form>
	<label for="quantidadeRecebimento">Vamos calcular? Informe o quanto você recebeu</label>
	<input type="text" id="quantidadeRecebimento" placeholder="R$" bind:value={salario} />
	<button on:click={handleInput}>Calcular</button>
</form>

{#if localValue.gastoFixo !== ''}
	<section>
		<h2>Divisão:</h2>
		<div>
			<Card title="Poupar" value={localValue.poupar} />
			<Card title="Gastos Fixos" value={localValue.gastoFixo} />
			<Card title="Gastos Variáveis" value={localValue.gastoVariavel} />
		</div>
	</section>
{/if}

<style>
	form {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		border: 1px solid #ccc;
		width: 150px;
	}

	section {
		margin-top: 2rem;
		text-align: center;
	}

	div {
		display: flex;
		gap: 1rem;
	}
</style>
