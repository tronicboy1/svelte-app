<script lang="ts">
  export let addNewItem: (title: string, contents: string) => void;

  let title: string;
  let contents: string;

  const handleSubmit = (event: Event) => {
    addNewItem(title, contents);
    title = "";
    contents = "";
  };
</script>

<form class="form" on:submit|preventDefault={handleSubmit}>
  <div>
    <label for="title">Title</label>
    <input type="text" name="title" bind:value={title} />
  </div>
  <div>
    <label for="contents">Contents</label>
    <input type="text" name="contents" bind:value={contents} />
  </div>
  <button type="submit">Add Item</button>
</form>

<style>
  .form {
    display: flex;
    flex-direction: column;
    text-align: left;
  }

  .form div {
    margin-bottom: 1rem;
  }

  .form label {
    margin-bottom: 0.3rem;
  }

  .form input {
    width: 100%;
  }
</style>
