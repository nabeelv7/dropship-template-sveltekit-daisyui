<script>
  import Footer from "$lib/components/Footer.svelte";
  import Carousel from "$lib/productcomponents/Carousel.svelte";
  import ProductText from "$lib/productcomponents/ProductText.svelte";
</script>

<section
  class="mx-auto md:py-30 py-10 px-5 grid md:grid-cols-2 grid-cols-1 gap-10 min-h-screen"
>
  <Carousel />
  <ProductText />
</section>
<Footer />
