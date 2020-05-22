<script context="module">

</script>

<script>
  import { onMount } from "svelte";
  import Parse from "parse/dist/parse";
  import { initClientParse } from "~/library/utils.js";

  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import MDBSpinner from "mdbsvelte/src/MDBSpinner.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";

  import Nav from "~/components/Nav.svelte";
  import PageTransition from "~/components/PageTransition.svelte";
  import Hero from "~/components/Hero.svelte";
  import ExampleGrid from "~/components/ExampleGrid.svelte";
  import CardGroup from "~/components/CardGroup.svelte";

  let loaded = false;

  var currentUser;

  onMount(async () => {
    initClientParse();
    if (process.browser) {
      currentUser = Parse.User.current();
    }
    loaded = true;
  });
</script>

<style lang="scss">

</style>

<svelte:head>
  <title>WELCOME</title>
</svelte:head>

<MDBContainer>
  <PageTransition>
    {#if loaded}
      <Hero />
      <CardGroup />
    {:else}
      <MDBContainer class="text-center">
        <MDBSpinner color="light" />
      </MDBContainer>
    {/if}
  </PageTransition>
</MDBContainer>
