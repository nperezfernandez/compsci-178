<script>
  let todos = [];
  let newTodo = "";

  function addTodo() {
    todos = [...todos, newTodo];
    newTodo = "";
  }

  function deleteTodo(index) {
    todos = todos.filter((_, i) => i !== index);
  }
</script>

<input bind:value={newTodo}>
<button on:click={addTodo}>Add Todo</button>

<ul>
  {#each todos as todo, index}
    <li>
      {todo}
      <button on:click={() => deleteTodo(index)}>Delete</button>
    </li>
  {/each}
</ul> 