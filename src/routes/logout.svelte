<script>
  import { goto } from "@sapper/app";
  import { onMount } from "svelte";
  import Parse from "parse/dist/parse";
  import { initClientParse } from "~/library/utils.js";
  import * as notifier from "@beyonk/svelte-notifications/src/notifier";

  onMount(async () => {
    initClientParse();
    if (process.browser) {
      Parse.User.logOut().then(() => {
        notifier.success("Successfully logged out!")
        goto("/");
      });
    }
  });
</script>
