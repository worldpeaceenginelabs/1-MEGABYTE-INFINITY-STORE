<script>
  let inputValue = '';
  let storedData = [];
  
  function handleInput(event) {
    inputValue = event.target.value;
  }

  function handleSubmit() {
    storedData = JSON.parse(localStorage.getItem('data')) || [];
    storedData.push(inputValue);
    localStorage.setItem('data', JSON.stringify(storedData));
    inputValue = '';
  }

  function handleDelete() {
    storedData = JSON.parse(localStorage.getItem('data')) || [];
    storedData.pop();
    localStorage.setItem('data', JSON.stringify(storedData));
  }

  function handleLocalStorageLimit() {
    console.log('Local storage size limit reached');
  }

  window.addEventListener('storage', event => {
    if (event.key === 'data' && event.newValue.length > 1048576) {
      handleLocalStorageLimit();
    }
  });
</script>

<fieldset>
<form>
<input type="text" bind:value={inputValue} on:input={handleInput} />
<button on:click|preventDefault={handleSubmit}>Send</button>
<button on:click|preventDefault={handleDelete}>Delete</button>
</form>


<ol>
  
  {#each storedData as item}
    <li>{item}</li>
  {/each}
  
</ol>
</fieldset>

<style>
fieldset{position: fixed; top: 1em; left: 1em;}

</style>