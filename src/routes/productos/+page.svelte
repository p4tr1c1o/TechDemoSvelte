<script>
	import DataTable, { Head, Body, Row, Cell } from '@smui/data-table';
	import Paper from '@smui/paper';
	import Button from '@smui/button';

	const productos = [
		{
			id: 1,
			nombre: '',
			categoria: '',
			precio: 100,
			estado: 'activo'
		}
	];

	function handleNuevoClick() {
		return;
	}
</script>

<h1>Hola Productos</h1>

<section class="container-centrado">
	<Paper>
		<div class="header-datatable">
			<Button variant="raised" on:click={handleNuevoClick}>+ Nuevo</Button>
		</div>
		<DataTable table$aria-label="User list" style="width: 100%;">
			<Head>
				<Row>
					<Cell numeric>Id</Cell>
					<Cell style="width: 100%;">Nombre</Cell>
					<Cell>Categoria</Cell>
					<Cell numeric>Precio</Cell>
					<Cell>Estado</Cell>
				</Row>
			</Head>
			<Body>
				{#each productos as producto (producto.id)}
					<Row>
						<Cell numeric>{producto.id}</Cell>
						<Cell>{producto.nombre}</Cell>
						<Cell>{producto.categoria}</Cell>
						<Cell numeric>{producto.precio.toFixed(2)}</Cell>
						<Cell>{producto.estado}</Cell>
					</Row>
				{/each}
			</Body>
		</DataTable>
	</Paper>
</section>

<style>
	.container-centrado {
		display: block;
		margin-left: auto;
		margin: 0 auto;
		max-width: 1200px;
	}
	.header-datatable {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		margin-bottom: 1rem;
	}
</style>
