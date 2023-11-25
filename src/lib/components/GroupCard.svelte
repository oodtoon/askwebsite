<script lang="ts">
  export let title: string;
  export let time: string;
  export let start: string | null = null;
</script>

<div class="group-container">
  <h4>{title}</h4>
  <p>{time}</p>
  {#if start}
    <p>{start}</p>
  {/if}
</div>

<style>
  .group-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
