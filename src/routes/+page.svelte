<script>
	import Dash from './Dash.svelte';
import Form from './Form.svelte'
</script>

<svelte:head>
	<title>Organização Financeira</title>
	<meta name="description" content="Svelte Organização Financeira" />
</svelte:head>

<section>
	<h1>Organização Financeira</h1>

	<h2>Vamos organizar suas finanças?</h2>

	<p>Como será feito a divisão?</p>

	<ul>
		<li>70% - Gastos fixos</li>
		<li>20% - Gastos variáveis</li>
		<li>10% - Poupar</li>
	</ul>
	<Form />
	<!-- <Dash /> -->
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}
</style>
