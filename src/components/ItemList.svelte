<script lang="ts">
import type ListItem from "../models/list-item";

  export let list: ListItem[];

  $: isEmpty = !list.length;

</script>

<section>
  {#if isEmpty}
  <p>No Items in List</p>
  {:else}
  <ul>
    {#each list as item (item.id)}
    <li>
      <h3>{item.title}</h3>
      <p>{item.contents}</p>
    </li>
    {/each}
  </ul>
  {/if}
</section>

<style>
  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  li {
    margin: 0 0 1rem 0;
    padding: 1rem;
    border: 1px solid grey;
    border-radius: 4px;
    text-align: left;
  }
  h3 {
    margin: 0 0 0.5rem 0;
  }
</style>