<script>
  import '@fontsource-variable/dm-sans';
  import Navbar from "$lib/components/Navbar.svelte";
  import "../app.css";

  let { children } = $props();
</script>

<Navbar />
{@render children()}
