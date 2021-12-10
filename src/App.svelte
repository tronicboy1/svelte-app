<script lang="ts">
  import NewItem from "./components/NewItem.svelte";
  import Card from "./components/UI/Card.svelte";
	import ItemList from "./components/ItemList.svelte";
	import type ListItem from "./models/list-item"

  let list: ListItem[] = [];

  const addNewItem = (title: string, contents: string) => {
    list = [...list, { id: Math.random().toString(12),title, contents}];
  };
</script>

<main>
  <Card>
    <NewItem {addNewItem} />
  </Card>
	<Card>
		<ItemList {list} />
	</Card>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
</style>
