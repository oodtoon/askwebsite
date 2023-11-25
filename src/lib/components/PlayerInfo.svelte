<script lang="ts">
  import Bullseye from "./icons/Bullseye.svelte";
  import Cap from "./icons/Cap.svelte";
  import Degree from "./icons/Degree.svelte";

  export let infoTitle: string;
  export let specialties: string;
  export let edu: string | null = null;

</script>

<div class="player-sheet">
  <div class="title">
    <div>{infoTitle}</div>
    <div class="icon">
      <Cap />
    </div>
  </div>

  <div class="specialties">
    <div class="icon">
      <Bullseye />
    </div>
    <div>{@html specialties}</div>
  </div>
  <br />
  {#if edu}
    <div class="degrees">
      <div>{edu}</div>
      <div class="icon">
        <Degree />
      </div>
    </div>
  {/if}
</div>

<style>
  .player-sheet {
    position: relative;
    padding: 2em 3em;
    background-color: rgb(62, 4, 69);
    color: white;
    font-size: 20px;
    margin: 4em 0;
    max-width: 920px;
  }

  .player-sheet::before {
    content: "";
    position: absolute;
    top: -30px;
    left: -30px;
    right: 30px;
    bottom: 20px;
    border: 10px solid white;
  }

  .title,
  .specialties,
  .degrees {
    display: flex;
    align-items: center;
    gap: 2em;
  }

  .icon {
    height: 50px;
    width: 50px;
  }

  @media (max-width: 320px) {
    .player-sheet {
      display: flex;
      flex-wrap: wrap;
      padding: 1em
    }

  .title,
  .specialties,
  .degrees {
    flex-wrap: wrap;
  }

  .player-sheet::before {
    content: "";
    position: absolute;
    top: -10px;
    left: -10px;
    right: 10px;
    bottom: 10px;
    border: 5px solid white;
  }

  }
</style>
