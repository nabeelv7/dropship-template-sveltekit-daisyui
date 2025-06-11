<script>
  import { config } from "$lib/config";
  const { store } = config;
</script>

<div class="navbar bg-base-200 max-w-screen-lg mx-auto">
  <div class="navbar-start">
    <div class="dropdown">
      <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h8m-8 6h16"
          />
        </svg>
      </div>
      <ul
        class="menu menu-md dropdown-content bg-base-100 rounded-box z-1 mt-3 w-60 p-2 shadow"
      >
        <li><a href="#products">Products</a></li>
        <li><a href="#testimonials">Testimonials</a></li>
        <li><a href="#faq">FAQ</a></li>
        <div class="divider"></div>
        <li>{@render FacebookButton()}</li>
      </ul>
    </div>
    <a href="/" class="font-bold text-xl">{store.name}</a>
  </div>
  <div class="navbar-center hidden lg:flex">
    <ul class="menu menu-horizontal px-1">
      <li><a href="#products">Products</a></li>
      <li><a href="#testimonials">Testimonials</a></li>
      <li><a href="#faq">FAQ</a></li>
    </ul>
  </div>
  <div class="md:flex hidden navbar-end">{@render FacebookButton()}</div>
</div>

{#snippet FacebookButton()}
  <!-- Facebook -->
  <a
    href={store.facebook_link}
    target="_blank"
    class="btn bg-[#1A77F2] text-white border-[#005fd8]"
  >
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
  </a>
{/snippet}
