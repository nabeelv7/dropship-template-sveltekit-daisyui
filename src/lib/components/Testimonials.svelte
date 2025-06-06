<script>
  let testimonials = [
    {
      name: "Akorn Veesle",
      image: "/images/Akorn.png",
      quote:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi ducimus repellat aperiam quam consequatur eligendi totam vitae iusto mollitia esse.",
    },
    {
      name: "Akorn Veesle",
      image: "/images/Akorn.png",
      quote:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi ducimus repellat aperiam quam consequatur eligendi totam vitae iusto mollitia esse Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi ducimus repellat aperiam quam consequatur eligendi totam vitae iusto mollitia esse.",
    },
    {
      name: "Akorn Veesle",
      image: "/images/Akorn.png",
      quote:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi ducimus repellat aperiam quam consequatur eligendi totam vitae iusto mollitia esse.",
    },
  ];
</script>

<div class="max-w-screen-lg mx-auto py-10 px-5" id="testimonials">
  <div class="text-center">
    <h1 class="text-3xl font-bold">🩷 Wall of Love</h1>
  </div>
  <div class="grid md:grid-cols-2 gridcols-cols-1 gap-4 py-10">
    {#each testimonials as testimonial, i}
      <div
        class={`border ${i == 1 ? "bg-secondary text-secondary-content" : "bg-base-100"} p-7 rounded-box drop-shadow-lg flex flex-col justify-around gap-2 ${i == 1 ? "md:row-span-2" : ""}`}
      >
        <div class="flex">
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
          <img src="star.svg" alt="&star;" class="h-6 w-6" />
        </div>
        <p class="italic text-xl">
          "{testimonial.quote}"
        </p>
        <div class="flex mt-5 items-center gap-3">
          <div class="avatar">
            <div class="w-14 rounded-full">
              <img
                src="https://img.daisyui.com/images/profile/demo/yellingcat@192.webp"
                alt={testimonial.name}
              />
            </div>
          </div>
          <p class={i == 1 ? "text-secondaey-content" : "text-base-content/80"}>
            &nbsp;-&nbsp;{testimonial.name}
          </p>
        </div>
      </div>
    {/each}
  </div>
</div>
