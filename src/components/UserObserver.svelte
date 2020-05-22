<script>
  import { goto } from "@sapper/app";
  import { onMount } from "svelte";
  export var currentUser;

  onMount(async () => {
    if (!currentUser) {
      goto("login");
    }
  });
</script>