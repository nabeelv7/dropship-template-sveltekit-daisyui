<script>
  import StarSvg from "./StarSVG.svelte";

  const avatars = [
    "https://img.daisyui.com/images/profile/demo/batperson@192.webp",
    "https://img.daisyui.com/images/profile/demo/spiderperson@192.webp",
    "https://img.daisyui.com/images/profile/demo/averagebulk@192.webp",
    "https://img.daisyui.com/images/profile/demo/wonderperson@192.webp",
  ];
</script>

<div class="py-20 flex items-center justify-center px-5">
  <div class="bg-base-100/60 border border-primary rounded-box p-10">
    <div class="max-w-screen-lg text-center flex flex-col gap-2">
      <h1 class="text-3xl font-bold">Buy Now</h1>
      <p class="text-opacity-80 text-gray-600">
        We are trusted by hundreds of happy customers
      </p>

      <div class="flex justify-center gap-1">
        {#each Array(5) as _}
          <StarSvg color="#f97316" />
        {/each}
      </div>

      <div class="avatar-group -space-x-6 flex justify-center">
        {#each avatars as avatar}
          <div class="avatar">
            <div class="w-12">
              <img src={avatar} alt="Happy customer avatar" />
            </div>
          </div>
        {/each}
      </div>

      <a href="#products" class="btn btn-primary mt-6">View Products &rarr;</a>
    </div>
  </div>
</div>
