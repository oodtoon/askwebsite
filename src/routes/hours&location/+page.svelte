<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import HrNLctnCard from "$lib/components/HrNLctnCard.svelte";
  import type { HoursNLocationInfo } from "$lib/types.js"

  const hoursInfoList: HoursNLocationInfo[] = [
    {
      type: "clock",
      title: "Monday - Friday | 8 AM - 7 PM Saturday | 9 AM - 11 AM"
    },

    {
      type: "teleHealth",
      title: "CONVENIENT TELEHEALTH SERVICES"
    },
    {
      type: "building",
      title: "85 Macomb Place Suite 102  Mt. Clemens, MI 48043"
    },
  ]

</script>

<div class="hours-container">
  <PageTitle title="HOURS & LOCATION"/>
  <div class="info-container">
    {#each hoursInfoList as hour}
      <HrNLctnCard type={hour.type} title={hour.title}/>
    {/each}
  </div>
</div>

<style>
  .hours-container {
    margin: 2em 4em;
    display: flex;
    flex-direction: column;
    gap: 2em;
    align-items: center;
  }

  .info-container {
    display: flex;
    flex-wrap: wrap;
    gap: 2em;
    justify-content: center;
    font-size: 20px;
  }
</style>