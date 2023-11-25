<script lang="ts">
  import type { HoursNLocation } from "$lib/types.ts";
  import Clock from ".//icons/Clock.svelte";
  import Building from "./icons/Building.svelte";
  import TeleHealth from "./icons/TeleHealth.svelte";
  export let type: HoursNLocation;
  export let title: string;
</script>

<div class="container">
  {#if type === "clock"}
    <div class="icon">
      <Clock />
    </div>
  {:else if type === "building"}
    <div class="icon">
      <Building />
    </div>
  {:else}
    <div class="icon">
      <TeleHealth />
    </div>
  {/if}
  <div class="info">
    {title}
  </div>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    max-width: 300px;
    gap: 2em;
    align-items: center;
  }

  .info {
    display: flex;
    color: rgb(62, 4, 69);
    background-color: white;
    text-align: center;
    padding: 1em;
  }


</style>
