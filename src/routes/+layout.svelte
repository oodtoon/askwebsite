<script lang="ts">
  import "../../src/index.css";
  import Nav from "$lib/components/Nav.svelte";
  import Footer from "$lib/components/Footer.svelte"

</script>

<svelte:head>
  <title>Ask</title>
</svelte:head>



<div>
  <main>
    <Nav></Nav>
    <slot />
    <Footer></Footer>
  </main>
</div>
