<script>

import {onMount, onDestroy, setContext} from 'svelte';
import { writable, get } from 'svelte/store';

//const active_wfi = writable(undefined);
//setContext('active-wfi', active_wfi); // who is listening ?

const selected = writable(undefined);
setContext('selected', selected); // what item is selected - exclusive. code

let selected_code = undefined;
setContext('selected-code', selected_code); // what item is selected - exclusive. code


const blist = [];
setContext('blist',blist)


$: {
  console.log('selected_code', selected_code)
}

selected.subscribe((e)=>{
  console.log('autorun:',e)
  console.log('blist',blist)
  blist.forEach(btn =>{
    if (btn.getAttribute('code') == e) {
      btn.classList.add('hotx')
    } else {
      btn.classList.remove('hotx')
    }
  })
})

</script>

<hbox>
<slot></slot>
</hbox>

<style>
hbox {
  width:100%;
  border: 1px solid green;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
