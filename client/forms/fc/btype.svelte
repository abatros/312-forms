<script>

import {onMount, onDestroy, setContext, getContext} from 'svelte';
import {get, set} from 'svelte/store'
export let code = undefined;

const selected = getContext('selected'); // svelte/store
const blist = getContext('blist'); // svelte/store
let selected_code = getContext('selected-code'); // svelte/store

console.log(`blist@10`, blist)

let btn;
let hot = false;

function onClick(e) {
  hot = !hot;
//  if (hot) btn.classList.add('hot')
//  else  btn.classList.remove('hot')
  console.log('click', e.target)
  if (hot) e.target.classList.add('hotx')
  else  e.target.classList.remove('hotx')
  selected.set(code)
  selected_code = code;
}


$m: {
  console.log(`selected:`, selected_code)
}

onMount(()=>{
  btn.classList.remove('hotx')
  blist.push(btn)
})

</script>

<hbox
  bind:this={btn}
  class = "hotx"
  on:click={onClick}
  code={code}>

<slot>Undefined</slot>

</hbox>


<style>
hbox {
  margin:1em;
  padding: 1em;
  border: 1px solid black;
  cursor: pointer;
}

.hotx {
  color: red;
  border: 1px solid red;
}

</style>
