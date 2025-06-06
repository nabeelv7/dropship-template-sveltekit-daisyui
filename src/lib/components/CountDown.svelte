<script>
  import { onMount } from "svelte";

  const TEN_DAYS_MS = 10 * 24 * 60 * 60 * 1000;

  let targetTime = Date.now() + TEN_DAYS_MS;
  let days = 0,
    hours = 0,
    minutes = 0,
    seconds = 0;

  function updateCountdown() {
    const now = Date.now();
    let diff = targetTime - now;

    // Reset when timer reaches 0
    if (diff <= 0) {
      targetTime = now + TEN_DAYS_MS;
      diff = TEN_DAYS_MS;
    }

    days = Math.floor(diff / (1000 * 60 * 60 * 24));
    hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    minutes = Math.floor((diff / (1000 * 60)) % 60);
    seconds = Math.floor((diff / 1000) % 60);
  }

  let intervalId;

  onMount(() => {
    updateCountdown();
    intervalId = setInterval(updateCountdown, 1000);
    return () => clearInterval(intervalId);
  });
</script>

<div class="grid auto-cols-max grid-flow-col gap-5 text-center bg-neutral">
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-pink-500 text-5xl">
      <span style={`--value:${days}`} aria-live="polite" aria-label={days}
        >{days}</span
      >
    </span>
    days
  </div>
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-pink-500 text-5xl">
      <span style={`--value:${hours}`} aria-live="polite" aria-label={hours}
        >{hours}</span
      >
    </span>
    hours
  </div>
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-pink-500 text-5xl">
      <span style={`--value:${minutes}`} aria-live="polite" aria-label={minutes}
        >{minutes}</span
      >
    </span>
    min
  </div>
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-pink-500 text-5xl">
      <span style={`--value:${seconds}`} aria-live="polite" aria-label={seconds}
        >{seconds}</span
      >
    </span>
    sec
  </div>
</div>
