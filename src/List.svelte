<script>
  let newItem = '';
  let todoList = [
    {text: "learn svelte", status: false},
    {text: "learn react", status: false},
    {text: "get a job", status: false},
  ];

  function addTodo() {
    todoList = [...todoList, {text: newItem, status: false}];
    newTodo = '';
  }

  function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
  }

</script>

<style>
  .checked {
    text-decoration: line-through;
  }
  .container {
    position: absolute;
    z-index: 9;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 80%;
    width: 100%;
  }
  .todo {
    border: 2px solid black;
    border-radius: 10px;
    width: 20%;
    font-size: larger;
    padding: 10px;
    margin: 5px 0px 5px 0px;
    align-self: center;
    text-align: left;
    cursor: move;
    z-index: 10;
  }
</style>

  <input bind:value={newItem} type="text" placeholder="New todo here...">
  <button on:click={addTodo}>Add</button>

  <div class="container">
    {#each todoList as item, index}
      <div class="todo">
        <input bind:checked={item.status} type="checkbox">
        <span class:checked={item.status}>{item.text}</span>
        <span on:click={() => removeFromList(index)}></span>
        <br/>
      </div>
    {/each}
  </div>
