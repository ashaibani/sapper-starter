<script>
  import { cubicInOut } from "svelte/easing";
  let duration = 200;
  let inDuration = 100;
  let delay = duration;

  const transitionIn = () => ({
    inDuration,
    delay,
    easing: cubicInOut,
    css: t => `opacity: ${t}`
  });

  const transitionOut = () => ({
    duration,
    delay: 0,
    easing: cubicInOut,
    css: t => `opacity: ${t}`
  });
</script>

<div in:transitionIn out:transitionOut>
  <slot />
</div>
