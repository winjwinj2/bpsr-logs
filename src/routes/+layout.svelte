<script lang="ts">
  import "../app.css";
  import { setupShortcuts } from "./main/settings/shortcuts";

  let { children } = $props();

  
  $effect.pre(() => {
    (async () => {
      await setupShortcuts();
    })();
  });
</script>

<svelte:window oncontextmenu={(e) => e.preventDefault()} />

{@render children()}
