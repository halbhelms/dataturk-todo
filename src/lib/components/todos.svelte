<script lang="ts">
  // import type { Todo } from '$lib/types';
  import todos from '$lib/seed-todos';

  import Todo from '$lib/components/todo.svelte';

  function complete(id: number) {
    console.log('changeFunction', id)
    const todo = todos.find(todo => todo.id === id);
    if (todo) {
      todo.completed = !todo.completed;
    }
  }
</script>



{#each todos as todo}
  <Todo {...todo} {complete}></Todo>
{/each}