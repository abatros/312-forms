<script>
  import { Meteor } from "meteor/meteor";
  import { LinksCollection } from '../imports/api/links';
  import F101 from './forms/f101.svelte'

  let subIsReady = false;
  $m: {
    const handle = Meteor.subscribe("links.all");
    subIsReady = handle.ready();
  }

  // more information about $m at https://atmospherejs.com/zodern/melte#tracker-statements
  let links;
  $m: links = LinksCollection.find().fetch();
</script>


<div class="container">
  <h1>Welcome to FORMS</h1>


  {#if subIsReady}
    <ul>
      {#each links as link (link._id)}
        <li><a href={link.url} target="_blank" rel="noreferrer">{link.title}</a></li>
      {/each}
    </ul>
  {:else}
    <div>Loading ...</div>
  {/if}


<F101> </F101>

</div>
