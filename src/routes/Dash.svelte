<script>
  import { getContext, onDestroy } from 'svelte';

const inputValue = getContext('inputValue');
let value;

console.log(getContext('inputValue'));


// const unsubscribe = inputValue.subscribe();

// onDestroy(() => {
//     unsubscribe();
// });
  
</script>