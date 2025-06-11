<script>
  import { config } from "$lib/config";
</script>

<div
  class="max-w-screen-lg mx-auto grid md:grid-cols-3 grid-cols-1 gap-5 py-5 items-center justify-between max-md:px-5 mb-5"
  id="products"
>
  {#each config.products as product}
    <div class="card bg-base-100">
      <figure>
        <img
          src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp"
          alt="Shoes"
        />
      </figure>
      <div class="card-body space-y-4">
        <div class="flex">
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
        </div>
        <h2 class="card-title text-2xl">{product.title}</h2>
        <p class="font-extrabold flex justify-between items-center">
          <span class="font-bold line-through text-xl"
            >${product.price + 0.35 * product.price}</span
          >
          <span
            class="text-green-500 text-3xl text-shadow-md text-shadow-green-300"
            >${product.price}</span
          >
        </p>
        <div class="card-actions justify-end">
          <button class="btn btn-block">View Information</button>
          <button class="btn btn-success btn-block"
            >Proceed to Checkout &rarr;</button
          >
        </div>
      </div>
    </div>
  {/each}
</div>
