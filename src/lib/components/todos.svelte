<script lang="ts">
  // import type { Todo } from '$lib/types';
  import seedTodos from '$lib/seed-todos';
  let todos = $state(seedTodos);

  import Todo from '$lib/components/todo.svelte';
  import Entry from '$lib/components/entry.svelte';

  function complete(id: number) {
    const todo = todos.find(todo => todo.id === id);
    if (todo) {
      todo.completed = true;
    }
  }

  function add(title: string) {
    const id = todos.length + 1;
    todos.push({ id, title, completed: false });
  }
</script>


<Entry {add}></Entry>
{#each todos as todo (todo.id)}
  <Todo {...todo} {complete}></Todo>
{/each}
