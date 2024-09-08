<script>
	export let title;
	export let value;
</script>

<div>
	<p>{title}</p>
	<p>R$ {value.replace('.', ',')}</p>
</div>

<style>
	div {
		background-color: white;
		width: 150px;
		height: 100px;
		border-radius: 8px;
	}
</style>
