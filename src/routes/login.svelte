<script context="module">

</script>

<script>
  import { goto } from "@sapper/app";
  import { onMount } from "svelte";
  import Parse from "parse/dist/parse";
  import { initClientParse } from "~/library/utils.js";
  import * as notifier from "@beyonk/svelte-notifications/src/notifier";

  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";
  import MDBSpinner from "mdbsvelte/src/MDBSpinner.svelte";

  import Nav from "~/components/Nav.svelte";
  import PageTransition from "~/components/PageTransition.svelte";
  import Login from "~/components/forms/Login.svelte";
  let loaded = false;
  var currentUser;

  onMount(async () => {
    initClientParse();
    if (process.browser) {
      currentUser = Parse.User.current();
      if (currentUser) {
        goto("/");
      }
      loaded = true;
    }
  });

  async function login(event) {
    let username = event.detail.username;
    let password = event.detail.password;
    try {
      currentUser = await Parse.User.logIn(username, password);
      notifier.success("Thank you for logging in!");
      goto("/");
    } catch (error) {
      notifier.danger(error.message);
    }
  }
</script>

<style lang="scss">

</style>

<svelte:head>
  <title>LOGIN</title>
</svelte:head>
<MDBContainer>
  <br />
  <br />

  <PageTransition>
    {#if loaded}
      <Login on:login={login} />
    {:else}
      <MDBContainer class="text-center">
        <MDBSpinner color="light" />
      </MDBContainer>
    {/if}
  </PageTransition>
</MDBContainer>
