<script context="module">

</script>

<script>
  import { onMount } from "svelte";
  import Parse from "parse/dist/parse";
  import { initClientParse } from "~/library/utils.js";
  import { goto } from "@sapper/app";
  import * as notifier from "@beyonk/svelte-notifications/src/notifier";

  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";
  import MDBSpinner from "mdbsvelte/src/MDBSpinner.svelte";

  import Nav from "~/components/Nav.svelte";
  import PageTransition from "~/components/PageTransition.svelte";
  import Signup from "~/components/forms/Signup.svelte";

  var currentUser;
  let loaded = false;

  onMount(async () => {
    initClientParse();
    if (process.browser) {
      currentUser = Parse.User.current();
      if (currentUser) {
        goto("/");
      }
    }
    loaded = true;
  });

  async function signUp(event) {
    var user = new Parse.User();
    let username = event.detail.username;
    let password = event.detail.password;

    user.set("username", username);
    user.set("password", password);
    try {
      await user.signUp();
      notifier.success("You've succeessfully signed up!");
      goto("/");
    } catch (error) {
      // Show the error message somewhere and let the user try again.
      notifier.danger("Error: " + error.code + " " + error.message);
    }
  }
</script>

<style lang="scss">

</style>

<svelte:head>
  <title>SIGNUP</title>
</svelte:head>
<MDBContainer>
  <br />
  <br />
  <PageTransition>
    {#if loaded}
      <Signup on:signUp={signUp} />
    {:else}
      <MDBContainer class="text-center">
        <MDBSpinner color="light" />
      </MDBContainer>
    {/if}
  </PageTransition>
</MDBContainer>
