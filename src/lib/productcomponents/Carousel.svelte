<script>
  let {
    images = [
      "https://img.daisyui.com/images/stock/photo-1494232410401-ad00d5433cfa.webp",
      "https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp",
      "https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp",
    ],
  } = $props();

  let selected = $state(0);
  let zoomX = $state(50);
  let zoomY = $state(50);
  let isHovering = $state(false);

  function handleMouseMove(e) {
    const { left, top, width, height } =
      e.currentTarget.getBoundingClientRect();
    zoomX = ((e.clientX - left) / width) * 100;
    zoomY = ((e.clientY - top) / height) * 100;
  }

  function selectImage(index) {
    selected = index;
  }
</script>

<div class="flex flex-col-reverse md:flex-row gap-6 items-start justify-end">
  <!-- Thumbnails -->
  <div class="flex md:flex-col gap-4">
    {#each images as img, index}
      <button
        type="button"
        onclick={() => selectImage(index)}
        class={`w-20 h-20 aspect-square rounded-md border-2 overflow-hidden transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 ${
          selected === index
            ? "border-black shadow-md"
            : "border-transparent opacity-60 hover:opacity-100"
        }`}
        aria-label={`Select image ${index + 1}`}
      >
        <img
          src={img}
          alt={`Thumbnail ${index + 1}`}
          class="w-full h-full object-cover"
        />
      </button>
    {/each}
  </div>

  <!-- Main Image -->
  <div
    class="flex-1 rounded-lg max-w-lg"
    onmousemove={handleMouseMove}
    onmouseenter={() => (isHovering = true)}
    onmouseleave={() => (isHovering = false)}
    role="region"
    aria-label="Zoomable product image"
  >
    <div class="overflow-hidden rounded-lg">
      <img
        src={images[selected]}
        alt="Selected Product"
        class="w-full aspect-square object-contain transition-transform duration-300 ease-in-out"
        style={`transform: scale(${isHovering ? 1.6 : 1}); transform-origin: ${zoomX}% ${zoomY}%;`}
      />
    </div>
  </div>
</div>
