<script>
import {onMount} from 'svelte';

export let attributes
//export let value = '';
//export let placeholder = '';

//console.log({})

export let width = `${4}rem`;

const {label, fontSize, name, value, placeholder='', color='black'} = attributes;


let input;
let invalid = false;

function every_change(e) {
  console.log(`Number/change:`,e)
  console.log(`Number/change value:`, input.value)
}

function every_input(e) {
  console.log(`Number/input:`,e)
  console.log(`Number/input value:`, input.value)
  invalid = isNaN(input.value)
  if (invalid) {
    input.classList.add('error')
  } else {
    input.classList.remove('error')
  }
}


onMount(()=>{
  input.classList.remove('error')
})

</script>


<label class="vbox">
  {label}
<input class="number error"
  bind:this={input}
  on:change={every_change}
  on:input={every_input}
  name={name}
  value={value}
  placeholder={placeholder}
  >
</label>

<style>



label {
  width: var(--width, 4rem);
  font-size: 0.8em;
  font-size: 1em;
  margin: 1em;
  padding: 0.4em;
  -width: 100%;
  min-height: 2em;
  -background-color: rgba(250,250,250,0.8);
  border-radius: 6px;
  align-items: flex-start;
  background-color: rgba(250, 250, 250, 0.8);
}

input {
  color: rgb(0,0,0,0.7);
  font-size: 1.4em;
  line-height: 1em;
  outline: none;
  border: none;
  background-color: transparent;
}

.error {
  color: red;
}

</style>
