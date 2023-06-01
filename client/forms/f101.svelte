<script>
import Input from './fc/input.svelte'
import Number from './fc/number.svelte'
//const o = {name:'firstname', value:'Peter'};

const attributes = {name:'firstname', value:'Peter'};

</script>

<vbox>

<hbox>

<Input --width="20em"
    attributes={{label:'First Name', name:'firstname', value:'Jane'}} />


<Input --width="20em"
  attributes={{label:'Last Name', name:'lastname', value:'Fonda'}} />

</hbox>




<hbox>

<Number
  --width="14em"
  attributes={{label:'Phone Number', name:'phone', value:'805-967-8457'}} />

<Number
  --width="10em" --color="rebeccapurple"
  attributes={{label:'Postal Code', name:'zip', value:'10112'}} />

</hbox>




</vbox>


<style>

vbox {
  background-color: rgba(80,120,200,0.5);
  width: 100%;
}


hbox {
  border: 1px dashed gray;
  margin: 1em 0;
}


</style>
