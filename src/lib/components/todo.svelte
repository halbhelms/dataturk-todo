<script lang="ts">
  interface Props {
    title: string;
    id: number;
    completed: boolean;
    complete: (id: number) => void;
  }
  
  let { title, id, completed, complete }: Props = $props();
</script>

<main>
  <div class="todo">
    <input type="checkbox" id="completed_{id}" onchange={() => complete(id)} />
    <label for="completed_{id}">{title}</label>
  </div>
</main>

<style>
  .todo {
    display: flex;
    align-items: center;
    padding: 0.5rem;
    border-bottom: 1px solid #ccc;
  }

  .title {
    margin-left: 1rem;
  } 

  input[type="checkbox"] {
    width: 1rem;
    height: 1rem;
  }
</style>