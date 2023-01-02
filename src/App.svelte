<script lang="ts">
  import dayjs from "dayjs";
  import { onMount } from "svelte";
  $: now = dayjs();

  onMount(() => {
    const interval = setInterval(() => {
      now = dayjs();
    }, 1000);

    return () => {
      clearInterval(interval);
    };
  });
</script>

<main>
  <h1>
    <span class="year">{now.format("YYYY")}</span>
    <span class="month">{now.format("MM")}</span>
    <span class="day">{now.format("DD")}</span>
    <span class="hour">{now.format("HH")}</span>
    <span class="minute">{now.format("mm")}</span>
  </h1>
</main>

<style>
  h1 {
    font-size: 70pt;
  }
  span:nth-child(even) {
    color: rebeccapurple;
  }
</style>
