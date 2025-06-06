<script>
  let products = [
    {
      title: "Product 1",
      price: 100,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
    {
      title: "Product 2",
      price: 200,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
    {
      title: "Product 3",
      price: 300,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
    {
      title: "Product 4",
      price: 400,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
    {
      title: "Product 5",
      price: 500,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
    {
      title: "Product 6",
      price: 600,
      image:
        "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60",
    },
  ];
</script>

<div
  class="max-w-screen-lg mx-auto grid md:grid-cols-3 grid-cols-1 gap-5 py-5 items-center justify-between px-5"
  id="products"
>
  {#each products as product}
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
          <button class="btn btn-accent btn-block">Add to Cart</button>
          <button class="btn btn-block">View Information</button>
        </div>
      </div>
    </div>
  {/each}
</div>
