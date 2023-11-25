<script lang="ts">
  import LearnMore from "$lib/components/icons/LearnMore.svelte";
  import ToTop from "$lib/components/icons/ToTop.svelte";
  export let type: string;
  export let img: string;
  export let top: string = "0";
  export let right: string = "0";
  export let isToTop: boolean = false;
  export let isLarge: boolean = false;
  export let id: string | null = null;
  export let handleAnchorClick: (e: any) => void;
</script>

<div class="link-container">
  <div class="img-container" class:small={!isLarge} class:isLarge>
    <div
      class="img"
      style:background-image="url({img})"
      style:background-position="top {top} right {right}"
    ></div>
  </div>
  <div class="info">
    {type}
  </div>
  <div class="anchor">
    {#if !isToTop}
      <a href={`#${id}`} on:click={handleAnchorClick}><LearnMore /></a>
    {:else}
      <a class="link-to-top" href="#top" on:click={handleAnchorClick}
        >Back To Top <ToTop /></a
      >
    {/if}
  </div>
</div>

<style>
  .link-container {
    display: flex;
    flex-direction: column;
    max-width: fit-content;
    gap: 2em;
  }

  .img-container {
    display: flex;
    overflow: hidden;
    border-radius: 50% 50% 4px 4px;
    border: 2px solid rgb(62, 4, 69);
    box-shadow:
      0.7px 0.6px 1px rgba(22, 22, 22, 0.5),
      2.3px 2.1px 3.5px -0.8px rgba(22, 22, 22, 0.5),
      5.7px 5.2px 8.7px -1.7px rgba(22, 22, 22, 0.5),
      13.8px 12.7px 21.1px -2.5px rgba(22, 22, 22, 0.5);
  }

  .small {
    width: 280px;
    height: 280px;
  }

  .isLarge {
    width: 300px;
    height: 300px;
  }

  .img {
    width: 100%;
    height: 100%;
    background-size: cover;
  }

  .info {
    display: flex;
    flex-wrap: wrap;
    background-color: rgb(62, 4, 69);
    color: white;
    font-size: 32px;
    padding: 0.5em;
    align-items: center;
    justify-content: center;
    box-shadow:
      0.7px 0.6px 1px rgba(22, 22, 22, 0.5),
      2.3px 2.1px 3.5px -0.8px rgba(22, 22, 22, 0.5),
      5.7px 5.2px 8.7px -1.7px rgba(22, 22, 22, 0.5),
      13.8px 12.7px 21.1px -2.5px rgba(22, 22, 22, 0.5);
  }

  .anchor {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  a {
    cursor: pointer;
    text-decoration: none;
  }

  .link-to-top {
    display: flex;
    align-items: center;
    font-size: 24px;
    font-weight: 500;
  }
</style>
