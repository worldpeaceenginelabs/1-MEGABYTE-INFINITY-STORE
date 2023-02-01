<script>
  import Gun from "gun/gun";
  import { onMount } from 'svelte';
  
  let db = Gun(['http://localhost:8765/gun']).get('XMBSTORES');
  let text ='';
  let newFieldValue, inputField;

  onMount(async () => {
    const store = db.get('1-megabyte-store');
    store.on(function(data, key){
      if(data) {
        text = data;
        localStorage.setItem('1-megabyte-store', data);
      } else {
        text = localStorage.getItem('1-megabyte-store') || '';
        store.put(text);
      }
    });
  });


</script>
<input type="text" bind:value={text}/>
<button on:click={() => db.get('1-megabyte-store').put(text)}>Save</button>