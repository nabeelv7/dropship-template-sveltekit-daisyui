<script>
  let faqs = [
    {
      question: "How do I create an account?",
      answer:
        'Click the "Sign Up" button in the top right corner and follow the registration process.',
    },
    {
      question: "I forgot my password. What should I do?",
      answer:
        'Click on "Forgot Password" on the login page and follow the instructions sent to your email.',
    },
    {
      question: "How do I update my profile information?",
      answer:
        'Go to "My Account" settings and select "Edit Profile" to make changes.',
    },
  ];
</script>

<div
  id="faq"
  class="max-w-screen-lg mx-auto grid md:grid-cols-2 grid-cols-1 px-5"
>
  <div>
    <h1 class="text-4xl font-bold">FAQ</h1>
  </div>
  <div class="mt-5 flex flex-col gap-2">
    {#each faqs as faq}
      <div class="collapse collapse-arrow bg-base-100 border border-base-300">
        <input type="radio" name="my-accordion-2" />
        <div class="collapse-title font-semibold">{faq.question}</div>
        <div class="collapse-content text-sm">{faq.answer}</div>
      </div>
    {/each}
  </div>
</div>
