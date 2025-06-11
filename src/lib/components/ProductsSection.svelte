<script>
  import { config } from "$lib/config";
  import { fade } from "svelte/transition";
  import StarSvg from "./StarSVG.svelte";

  let activeImageIndex = $state({});

  const showSecondImageDef = (id) => {
    activeImageIndex[id] = 1;
    activeImageIndex = { ...activeImageIndex };
    setTimeout(() => {
      activeImageIndex[id] = 0;
      activeImageIndex = { ...activeImageIndex };
    }, 500);
  };
</script>

<div
  class="max-w-screen-lg mx-auto grid md:grid-cols-3 grid-cols-1 gap-5 py-5 items-center justify-between max-md:px-5 mb-5"
  id="products"
>
  {#each config.products as product}
    <article
      class="card bg-base-100"
      onmouseover={() => showSecondImageDef(product.id)}
      onfocus={() => showSecondImageDef(product.id)}
      role="region"
      aria-label={`Product: ${product.title}`}
    >
      <figure class="w-full aspect-[4/3] overflow-hidden relative">
        <a
          href={`/products/${product.id}`}
          class="block w-full h-full relative"
        >
          {#if activeImageIndex[product.id] === 0 || activeImageIndex[product.id] == null}
            <enhanced:img
              src="/static/product1/1.jpg"
              alt={`picture of the product: ${product.title}`}
              class="object-cover w-full h-full absolute top-0 left-0"
              transition:fade
            />
          {/if}
          {#if activeImageIndex[product.id] === 1}
            <enhanced:img
              src="/static/product1/2.jpg"
              alt={`alternate picture of the product: ${product.title}`}
              class="object-cover w-full h-full absolute top-0 left-0"
              transition:fade
            />
          {/if}
        </a>
      </figure>

      <div class="card-body space-y-4">
        <div class="flex">
          {#each Array(5) as _, i}
            <StarSvg color="#f97316" />
          {/each}
        </div>
        <h2 class="card-title text-2xl">{product.title}</h2>
        <p class="font-extrabold flex justify-between items-center">
          <span class="font-bold line-through text-xl">
            ${product.price + 0.35 * product.price}
          </span>
          <span
            class="text-green-500 text-3xl text-shadow-md text-shadow-green-300"
          >
            ${product.price}
          </span>
        </p>
        <div class="card-actions justify-end">
          <a href={`/products/${product.id}`} class="btn btn-block"
            >View Information</a
          >
          <button class="btn btn-success btn-block"
            >Proceed to Checkout &rarr;</button
          >
        </div>
      </div>
    </article>
  {/each}
</div>
