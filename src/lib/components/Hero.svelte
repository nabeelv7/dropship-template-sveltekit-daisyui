<script>
  import Banner from "./Banner.svelte";
</script>

<div class="mx-auto max-w-screen-lg">
  <Banner />
  <div class="flex w-full items-center justify-between py-10">
    <div class="flex flex-col gap-2 max-w-md">
      <h1 class="text-3xl font-bold">RestNest</h1>
    </div>
    <!-- Facebook -->
    <button class="btn bg-[#1A77F2] text-white border-[#005fd8]">
      <svg
        aria-label="Facebook logo"
        width="16"
        height="16"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 32 32"
        ><path
          fill="white"
          d="M8 12h5V8c0-6 4-7 11-6v5c-4 0-5 0-5 3v2h5l-1 6h-4v12h-6V18H8z"
        ></path></svg
      >
      Contact on Facebook
    </button>
  </div>
</div>
