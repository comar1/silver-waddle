<script>
  let todos = [];
  let task = "";

  const addTodo = () => {
    let todo = {
      task: "",
      isComplete: false,
      createdAt: new Date(),
    };
    todos = [...todos, todo];
  };

  $: console.table(todo);
</script>

<input type="text" bind:value={todo.task} />
<button on:click={addTodo}>Add</button>

<ol>
  {#each todos as todo}
    <li class:complete={todo.isComplete}>{todo.task}</li>
  {/each}
</ol>

<style>
  .complete {
    text-decoration: line-through;
  }
</style>
