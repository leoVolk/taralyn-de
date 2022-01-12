<template>
  <div
    class="w-full min-h-screen flex xl:flex-nowrap flex-wrap relative overflow-y-hidden bg-amber-50 dark:bg-gray-900 dark:text-gray-100"
  >
    <div
      class="xl:w-1/2 xl:h-auto min-h-screen w-full flex flex-col flex-wrap relative"
    >
      <div class="items-center flex h-full">
        <div class="xl:p-8 p-4">
          <h1
            class="tnr text-6xl md:text-9xl xl:text-[12rem] xl:text-left text-center font-medium tracking-wide"
          >
            Hi, I'm Taralyn!
          </h1>

          <p class="tracking-wide xl:max-w-screen-lg xl:mt-12 mt-6 xk:text-lg">
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua. <br />At vero eos et accusam et justo duo
            dolores et ea rebum. Stet clita kasd gubergren, no sea takimata
            sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet,
            consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt
            ut labore et dolore magna aliquyam erat, sed diam voluptua.
          </p>

          <div class="flex flex-row mt-12 items-center justify-between">
            <div class="xl:w-auto w-full">
              <nuxt-link
                to=""
                class="border-4 border-black dark:border-gray-100 font-medium text-2xl xl:px-32 py-2 hover:bg-black dark:hover:bg-gray-100 dark:hover:text-gray-900 hover:text-white transition-all duration-300 flex xl:block justify-center"
                ><span>About Me</span></nuxt-link
              >
            </div>
          </div>
        </div>
      </div>

      <corner-borders></corner-borders>
    </div>
    <div class="xl:w-1/2 w-full">
      <div
        class="flex xl:flex-nowrap flex-wrap flex-row items-end xl:h-full h-screen"
      >
        <nuxt-link
          to="/gallery"
          class="xl:border-r-4 xl:border-l-4 border-black dark:border-gray-100 category relative animate__animated animate__slideInUp"
          style=""
        >
          <img
            class=""
            src="https://images.unsplash.com/photo-1484589065579-248aad0d8b13?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=918&q=80"
          />
          <div class="flex xl:items-end items-center justify-center h-full">
            <div class="xl:-rotate-90 xl:-translate-y-[200%]">
              <h2 class="">Gallery</h2>
            </div>
          </div>
        </nuxt-link>
        <nuxt-link
          to="/cosplay"
          class="xl:border-r-4 border-black dark:border-gray-100 category relative animate__animated animate__slideInUp animate__delay-025s"
        >
          <img
            class=""
            src="https://images.unsplash.com/photo-1567095761054-7a02e69e5c43?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
          />
          <div class="flex xl:items-end items-center justify-center h-full">
            <div class="xl:-rotate-90 xl:-translate-y-[200%]">
              <h2 class="">Cosplay</h2>
            </div>
          </div>
        </nuxt-link>
        <nuxt-link
          to="/blog"
          class="xl:border-r-4 border-black dark:border-gray-100 category relative animate__animated animate__slideInUp animate__delay-050s"
        >
          <img
            class=""
            src="https://images.unsplash.com/photo-1556139954-ec19cce61d61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
          />
          <div class="flex xl:items-end items-center justify-center h-full">
            <div class="xl:-rotate-90 xl:-translate-y-[200%]">
              <h2 class="">Blog</h2>
            </div>
          </div>
        </nuxt-link>
        <nuxt-link
          to="/blog"
          class="category relative animate__animated animate__slideInUp animate__delay-075s"
        >
          <img
            class=""
            src="https://images.unsplash.com/photo-1615615307921-1f456bc82a08?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
          />
          <div class="flex xl:items-end items-center justify-center h-full">
            <div class="xl:-rotate-90 xl:-translate-y-[200%]">
              <h2 class="relative z-10">Contact</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import CornerBorders from '~/components/CornerBorders.vue'
export default {
  components: { CornerBorders },
  name: 'IndexPage',
}
</script>

<style lang="postcss">
.category {
  @apply xl:w-1/4 w-full hover:w-[30%] transition-all duration-300 bg-cover xl:h-full h-1/4 cursor-pointer bg-black;
}

.category img {
  @apply object-cover w-full transition-all duration-300 absolute inset-0 h-full hover:grayscale;
}

.category h2 {
  @apply text-6xl font-bold tracking-wider text-white z-10 relative;
}
</style>
