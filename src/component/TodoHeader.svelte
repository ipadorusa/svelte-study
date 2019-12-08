<script>
  import { onMount } from "svelte";
  import { itemStore } from "../store/store";

  const getList = async () => {
    const res = await fetch('https://bookmarker-cbbb9.firebaseio.com/')
    .then(response => response.json())
    .then(json => console.log(json))
  }


  let value;
  onMount(() => {
    getList();
  });
  const handleAddItem = () => {
    itemStore.addItem(value);
    value = "";
  };

  
</script>
<style>
  .disabled {
    color: graytext;
  }
</style>
<input type="text" bind:value placeholder="Item name" />
<button on:click={handleAddItem} disabled={!value} class:disabled={!value}>
  Add Item
</button>