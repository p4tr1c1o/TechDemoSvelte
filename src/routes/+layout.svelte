<script>
	import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
	import Drawer, { AppContent, Content, Header, Subtitle } from '@smui/drawer';
	import IconButton from '@smui/icon-button';
	import List, { Item } from '@smui/list';

	let open = false;

	function handleMenuClick() {
		open = !open;
	}
</script>

<TopAppBar variant="static">
	<Row>
		<Section>
			<IconButton class="material-icons" on:click={handleMenuClick}>menu</IconButton>
			<Title>
				<a href="/">Home</a>
			</Title>
		</Section>
		<Section align="end" toolbar>
			<IconButton class="material-icons" aria-label="Download">file_download</IconButton>
			<IconButton class="material-icons" aria-label="Print this page">print</IconButton>
			<IconButton class="material-icons" aria-label="Bookmark this page">bookmark</IconButton>
		</Section>
	</Row>
</TopAppBar>

<Drawer variant="dismissible" bind:open>
	<Header>
		<Title>Super Drawer</Title>
		<Subtitle>It's the best drawer.</Subtitle>
	</Header>
	<Content>
		<List>
			<Item href="/productos">Productos</Item>
		</List>
	</Content>
</Drawer>

<AppContent>
	<main>
		<slot />
	</main>
</AppContent>

<style>
	main {
		height: 100%;
	}
</style>
