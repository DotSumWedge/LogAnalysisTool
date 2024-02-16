<script>
    import { createEventDispatcher } from 'svelte';
  
    const dispatch = createEventDispatcher();
  
    let userInput = '';
  
    function handleSubmit() {
      dispatch('submit', { userInput });
    }
  </script>
  
  <form on:submit|preventDefault={handleSubmit}>
    <textarea bind:value={userInput} placeholder="Describe your analysis perspective..."></textarea>
    <button type="submit">Analyze</button>
  </form>
  