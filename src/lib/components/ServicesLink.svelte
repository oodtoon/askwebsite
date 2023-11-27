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
    border: 2px solid var(--ask-purple);
    box-shadow: var(--ask-shadow)
  }

  .small {
    width: clamp(150px, 260px, 290px);
    height: clamp(150px, 260px, 290px);
  }

  .isLarge {
    width: clamp(150px, 300px, 310px);
    height: clamp(150px, 300px, 310px);
  }

  .img {
    width: 100%;
    height: 100%;
    background-size: cover;
  }

  .info {
    display: flex;
    flex-wrap: wrap;
    background-color: var(--ask-purple);
    color: white;
    font-size: 32px;
    padding: 0.5em;
    align-items: center;
    justify-content: center;
    box-shadow: var(--ask-shadow);
  }

  .anchor {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  a {
    text-decoration: none;
  }

  .link-to-top {
    display: flex;
    align-items: center;
    font-size: 24px;
    font-weight: 500;
  }

  @media (max-width: 320px) {
    .isLarge {
      width: clamp(150px, 260px, 290px);
      height: clamp(150px, 260px, 290px);
    }
  }
</style>
