<script>
  import Banner from "./Banner.svelte";
  import CountDown from "./CountDown.svelte";
</script>

<div class="mx-auto max-w-screen-lg drop-shadow-2xl">
  <Banner />
  <div class="flex flex-col justify-center items-center pt-13 pb-5 bg-neutral">
    <h1 class="capitalize text-neutral-content py-3 font-extrabold">🎉 35% OFF FOR THE NEXT 10 DAYS</h1>
      <CountDown />
  </div>
</div>
