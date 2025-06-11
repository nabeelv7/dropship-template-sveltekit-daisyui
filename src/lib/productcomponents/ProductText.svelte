<script>
  import { page } from "$app/state";
  import { config } from "$lib/config";

  const product = config.products[page.params.id - 1];

  let count = $state(1);

  const increment = () => count++;
  const decrement = () => {
    if (count > 1) count--;
  };
</script>

<div class="flex flex-col gap-6 max-w-md break-words">
  <!-- Product Title -->
  <h1 class="text-4xl font-extrabold capitalize">
    {product?.title}
  </h1>

  <!-- Key Features -->
  <ul class="flex flex-col gap-2 text-lg">
    {#each product.keyfeatures as feature}
      <li class="flex items-center gap-2">
        <span>{feature}</span>
      </li>
    {/each}
  </ul>

  <!-- Quantity Selector -->
  <div class="flex items-center gap-2">
    <button onclick={decrement} class="btn text-2xl px-4">-</button>
    <div class="text-2xl font-semibold w-16 text-center">{count}</div>
    <button onclick={increment} class="btn text-2xl px-4">+</button>
  </div>

  <!-- Color Variants -->
  <div class="flex flex-col gap-2">
    <h2 class="text-lg font-bold">Colors:</h2>
    <div class="flex gap-3">
      <a
        href="#slide2"
        aria-label="white variant"
        class="w-10 h-10 rounded-md bg-white border-2 border-black"
      ></a>
      <a
        href="#slide7"
        aria-label="black variant"
        class="w-10 h-10 rounded-md bg-black border-2 border-black"
      ></a>
      <a
        href="#slide8"
        aria-label="green variant"
        class="w-10 h-10 rounded-md bg-emerald-600 border-2 border-black"
      ></a>
    </div>
  </div>

  <!-- Pricing Info -->
  <div class="flex flex-col gap-1">
    <p class="text-base text-error line-through">
      ${count * (product.price + product.price * 0.35)}
    </p>
    <h2 class="text-2xl font-bold">
      Total: <span class="text-success">{count * product.price} USD</span>
    </h2>
  </div>

  <!-- Checkout Button -->
  <a href="/checkout" class="btn btn-accent w-full md:w-80 text-center">
    Proceed to Checkout &rarr;
  </a>
</div>
