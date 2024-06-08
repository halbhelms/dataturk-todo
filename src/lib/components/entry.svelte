<script lang="ts">
  interface Props {
    add: (title: string) => void;
  }

  let { add }: Props = $props();
  let input: string = $state('')

  function submit(event: Event) {
    event.preventDefault();
    add(input);
    input = '';
  }
</script>

<main>
  <form> 
    <input type="text" name="title" onblur={submit} bind:value={input} placeholder="What needs to be done?" /> 
    <!-- <input type="submit" value="Add" ={submit}/> 3 -->
  </form>
</main>


<style>
  main {
    display: flex;
    justify-content: center;
    padding: 1rem;
    width: 20rem;
  }

  form {
    display: flex;
    width: 100%;
  }

  input[type="text"] {
    width: 100%;
    padding: 0.5rem;
    font-size: 1rem;
    border: 1px solid #ccc;
  }
</style>