<script>
  import '../css/todo.css';

  let items = [
    { id: 1, name: "Milk", done: false },
    { id: 2, name: "Bread", done: true },
    { id: 3, name: "Eggs", done: false }
  ];
  const remove = item => {
    items = items.filter(i => i !== item);
  };
  let name = "";
  const addItem = (e) => {
    e.preventDefault();
    items = [...items, 
      {
        id: Math.random(),
        name,
        done: false
      }
    ]
  }
</script>
<h1>Grocery List 🗒️</h1>
<form on:submit={addItem}>
  <label for="name">Add an item</label>
  <input id="name" type="text" bind:value={name} />
</form>
<ul>
    {#each items as item}
      <li class:done={item.done}>
        <input type="checkbox" bind:checked={item.done} />
        <span>{item.name}</span>
        <button on:click={() => remove(item)}>&times;</button>
      </li>
    {/each}
  </ul>