<script lang="ts">
  import Schedule from "./icons/Schedule.svelte";
  import ToTop from "./icons/ToTop.svelte";

  export let img: string;
  export let title: string;
  export let name: string;
  export let degree: string;
  export let translate: string = "0, 0";
  export let scale: string = "1";
  export let hasLink: boolean = false;
  export let id: string | null = null;

  function handleAnchorClick(event: any) {
    event.preventDefault();
    const link = event.currentTarget as HTMLAnchorElement;
    const anchorId = new URL(link.href).hash.replace("#", "");
    const anchor = document.getElementById(anchorId);
    window.scrollTo({
      top: anchor!.offsetTop,
      behavior: "smooth",
    });
  }
</script>

<div class="player-container">
  {#if !hasLink}
    <a class="img-container" href={`#${id}`} on:click={handleAnchorClick}>
      <img
        src={img}
        alt="Team Player"
        style:transform={`scale(${scale}) translate(${translate})`}
      />
    </a>
  {:else}
    <div class="img-container">
      <img
        src={img}
        alt="Team Player"
        style:transform={`scale(${scale}) translate(${translate})`}
      />
    </div>
  {/if}

  <div class="title">{title}</div>
  {#if !hasLink}
    <div class="player-info">
      <div class="name"><b>{name}</b></div>
      <div>{degree}</div>
    </div>
  {:else}
    <div class="link">
      <a href="/contact">
        <div class="link-svg">
          <Schedule />
          <span class="link-description">Schedule Consultation</span>
        </div>
      </a>
    </div>
    <div>
      <a class="link-to-top" href="#top" on:click={handleAnchorClick}
        >Back To Top <ToTop /></a
      >
    </div>
  {/if}
</div>

<style>
  .player-container {
    display: flex;
    flex-direction: column;
    gap: 1em;
    max-width: 350px;
    align-items: center;
    font-size: 24px;
  }

  .player-info {
    background-color: white;
    text-align: center;
    color: var(--ask-purple);
    padding: 1em 0.5em;
    border-radius: 4px;
    box-shadow: var(--ask-shadow)
  }

  .img-container {
    overflow: hidden;
    max-width: 300px;
    aspect-ratio: 1/1;
    border-radius: 50%;
    box-shadow: var(--ask-shadow)
  }

  img {
    max-width: 100%;
    height: auto;
  }

  .title {
    background-color: var(--ask-purple);
    color: white;
    padding: 0.5em;
    border-radius: 8px;
    font-weight: 200;
    box-shadow: var(--ask-shadow)
  }

  .name {
    font-size: 32px;
  }

  .link-svg {
    display: flex;
    position: relative;
    max-width: 200px;
  }

  .link-description {
    position: absolute;
    font-size: 16px;
    right: 10px;
    top: 15px;
  }

  .link-to-top {
    display: flex;
    align-items: center;
    font-size: 24px;
    font-weight: 500;
  }

  @media (max-width: 320px) {
    .img-container {
      height: 150px;
      width: 150px;
    }
  }
</style>
