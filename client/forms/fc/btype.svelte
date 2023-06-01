<script>

export let code = undefined;

</script>

<hbox code={code}>
<slot>Undefined</slot>
</hbox>


<style>
hbox {
  margin:1em;
  padding: 1em;
  border: 1px solid black;
  cursor: pointer;
}
</style>
