<script>
  import { onMount } from "svelte";
  import Parse from "parse/dist/parse";
  import { initClientParse } from "~/library/utils.js";

  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import Nav from "~/components/Nav.svelte";
  import Notifications from "@beyonk/svelte-notifications/src/Notifications";
  import Footer from "~/components/Footer.svelte";

  var currentUser;

  onMount(async () => {
    initClientParse();
    if (process.browser) {
      currentUser = Parse.User.current();
    }
  });
</script>

<style lang="scss">

</style>

<svelte:head>
  <meta name="version" content="pkg.version" />
</svelte:head>
<MDBContainer>
  <Nav {currentUser} />
  <main>
    <Notifications />
    <slot />
  </main>
  <Footer />
</MDBContainer>
