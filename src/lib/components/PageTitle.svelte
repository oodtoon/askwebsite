<script lang="ts">
  export let title: string;
  let outerWidth: number;
</script>

<svelte:window bind:outerWidth />

<div class="title-container">
  {#if outerWidth > 769}
    <img
      class="title-img"
      src="https://askpsychologicalservices.com/images/3cc98553e78333ece2ac284d66c46fbb.png"
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
      src="https://askpsychologicalservices.com/images/3cc98553e78333ece2ac284d66c46fbb.png"
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
    height: 100%;
    border-radius: 50% 50% 0 0;
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

    .title-img {
      width: 20%;
    }
  }

  @media (max-width: 320px) {
    .title-img {
      width: 50%;
    }
  }
</style>
