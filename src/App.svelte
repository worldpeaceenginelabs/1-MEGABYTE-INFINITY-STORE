<script>
    let inputValue = '';
  
    function handleInput(event) {
      inputValue = event.target.value;
    }
  
    function handleSubmit() {
      const storedData = JSON.parse(localStorage.getItem('data')) || [];
      storedData.push(inputValue);
      localStorage.setItem('data', JSON.stringify(storedData));
      inputValue = '';
      console.log(storedData);
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
  
  <input type="text" bind:value={inputValue} on:input={handleInput} />
  <button on:click={handleSubmit}>Send</button>
  