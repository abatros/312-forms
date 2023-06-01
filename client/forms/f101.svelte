<script>
import Input from './fc/input.svelte'
import Number from './fc/number.svelte'
import Phone_number from './fc/phone-number.svelte'
import BType from './fc/btype.svelte'
import Group from './fc/group.svelte'

//const o = {name:'firstname', value:'Peter'};

const attributes = {name:'firstname', value:'Peter'};

let selected = 1;

const items = [
  'temple', 'hospital', 'residency',
  'public'
]


</script>

<vbox>

<hbox>

<Input --width="20em" label="First Name"  --color="rebeccapurple"
    attributes={{name:'firstname', value:'Jane'}} />


<Input --width="20em" label="Last Name"
  attributes={{name:'lastname', value:'Fonda'}} />

</hbox>




<hbox>

<Phone_number label="Phone Number"
  --width="14em"
  attributes={{name:'phone', value:'805-967-8457'}} />

<Number --width="6em" label='Extension'
  attributes={{ name:'phonex', value:''}} />


<Number label="Postal Code",
  --width="10em"
  attributes={{name:'zip', value:'10112'}} />

</hbox>

<!--
    components will show horizontally, and wrap.
-->

<hbox class="wrap">

  <Input --width="100%" label="Street Name"
      attributes={{name:'firstname', value:''}} />


</hbox>



<Group class="vbox wrap">

{#each items as item, j}

  <label>
  	<input type=radio bind:group={selected} value={1+j}>
  	{item}
  </label>

{/each}

</Group>


<Group>

<h3 class="label">public</h3>


    <BType code="HC">Health Care Center</BType>
    <BType code="HP">Hospital</BType>

    <BType code="DC">Day Care Center</BType>
    <BType code="CH">Temple / Church</BType>
    <BType code="SC">School</BType>
    <BType code="GM">Government</BType>
    <BType code="PA">Arena/Public Assembly</BType>
    <BType code="PR">Prison</BType>
    <BType code="PK">Park</BType>
    <BType code="EN">Entertainment</BType>
    <BType code="GO">Golf Course Clubhouse</BType>


<h3 class="label">Commercial</h3>


    <BType code="PL">Parking Lot / Structure</BType>
    <BType code="SP">Shopping Center / Retail</BType>
    <BType code="MT">Motel / Hotel</BType>
    <BType code="WH">Warehouse</BType>

    <BType code="SI">Light Industry/Office (&lt;200 คน)</BType>
    <BType code="LI">Large Industry/Office (200-1000 คน)</BType>
    <BType code="MA">Manufacturing (&lt;1000 คนขึ้นไป)</BType>



    <h3 class="label">Residential</h3>



  <BType code="CO">Apartment/Condo</BType>
  <BType code="DU">Duplex</BType>

  <BType code="MF">Multi Family</BType>
  <BType code="OT">Other</BType>
  <BType code="SF">Single Family</BType>
  <BType code="UN">Unknown</BType>
  <BType code="X">Cancel Building</BType>


</Group>



</vbox>


<style>

h3 {
  width:100%;
}

vbox {
  background-color: rgba(80,120,200,0.5);
  width: 100%;
}


.building-types {
  width:100%;
}

hbox {
  border: 1px dashed gray;
  margin: 1em 0;
}

hbox.wrap {

}


</style>
