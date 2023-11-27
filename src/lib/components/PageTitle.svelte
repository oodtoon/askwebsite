<script lang="ts">
  import logo from "$lib/images/AskLogo.png"
  export let title: string;
  let outerWidth: number;

  let imgLogo = "https://askpsychologicalservices.com/images/3cc98553e78333ece2ac284d66c46fbb.png"
</script>

<svelte:window bind:outerWidth />

<div class="title-container">
  {#if outerWidth > 769}
    <img
      class="title-img"
      src={logo}
      alt="ask-logo"
    />
  {/if}
  <span>
    <h1 class="title">{title}</h1>
    <h2 class="sub-title">ASK Psychological Services</h2>
  </span>
  {#if outerWidth <= 769}
    <img
      class="title-img"
      src={logo}
      alt="ask-logo"
    />
  {/if}
</div>

<style>
  .title-container {
    grid-area: title;
    display: flex;
    align-items: center;
    gap: 2em;
  }

  .title-img {
    width: clamp(100px, 200px, 300px);
    height: clamp(100px, 200px, 300px);
    border-radius: 50% 50% 0 0;
    margin: 0;
  }

  .title {
    font-size: 60px;
    margin: 1rem 0;
  }

  .sub-title {
    margin: 0;
    font-weight: 100;
    font-size: 32px;
  }

  @media (max-width: 769px) {
    .title-container {
      flex-wrap: wrap;
      justify-content: center;
    }

    .title {
      font-size: 40px;
    }

    .title-img {
      margin: auto;
    }
  }

  @media (max-width: 320px) {
    .title {
      font-size: 30px;
    }

    .title-img {
      height: 150px;
      width: 150px;
    }
  }
</style>
