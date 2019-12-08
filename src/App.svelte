<script>
  import TodoHeader from "./component/TodoHeader.svelte";
  import TodoList from "./component/TodoList.svelte";
  import { itemStore } from "./store/store";
</script>
<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
</style>
<main>
  <div>Total item: {$itemStore.length}</div>
  <TodoHeader />
  <TodoList />
</main>