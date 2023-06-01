<script>
export let attributes
//export let value = '';
//export let placeholder = '';

//console.log({})

let input;
export let width = `${4}rem`;

const {label, fontSize, name, value, placeholder='', color='black'} = attributes;

</script>


<label class="vbox">
  {label}
<input
  type="text"
  bind:this={input}
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


</style>
