<script>
  import { onMount } from "svelte";

  const TARGET_DAYS = [10, 20, 30];

  let targetTime;
  let days = 0,
    hours = 0,
    minutes = 0,
    seconds = 0;

  function getNextTargetDate() {
    const now = new Date();
    const currentDay = now.getDate();
    const currentMonth = now.getMonth();
    const currentYear = now.getFullYear();

    for (let day of TARGET_DAYS) {
      if (currentDay < day) {
        return new Date(currentYear, currentMonth, day, 0, 0, 0, 0).getTime();
      }
    }

    // After 30th, go to the 10th of next month
    const nextMonth = currentMonth === 11 ? 0 : currentMonth + 1;
    const nextYear = currentMonth === 11 ? currentYear + 1 : currentYear;
    return new Date(nextYear, nextMonth, 10, 0, 0, 0, 0).getTime();
  }

  function updateCountdown() {
    const now = Date.now();
    let diff = targetTime - now;

    if (diff <= 0) {
      targetTime = getNextTargetDate();
      diff = targetTime - now;
    }

    days = Math.floor(diff / (1000 * 60 * 60 * 24));
    hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    minutes = Math.floor((diff / (1000 * 60)) % 60);
    seconds = Math.floor((diff / 1000) % 60);
  }

  let intervalId;

  onMount(() => {
    targetTime = getNextTargetDate();
    updateCountdown();
    intervalId = setInterval(updateCountdown, 1000);
    return () => clearInterval(intervalId);
  });
</script>

<div class="grid auto-cols-max grid-flow-col sm:gap-5 gap-1 text-center bg-neutral">
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-pink-500 text-5xl">
      <span style={`--value:${days}`} aria-live="polite" aria-label={days}
        >{days}</span
      >
    </span>
    days
  </div>
  <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
    <span class="countdown text-shadow-sm text-shadow-primary text-5xl">
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
    <span class="countdown text-shadow-sm text-shadow-primary text-5xl">
      <span style={`--value:${seconds}`} aria-live="polite" aria-label={seconds}
        >{seconds}</span
      >
    </span>
    sec
  </div>
</div>
