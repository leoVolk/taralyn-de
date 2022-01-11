<template>
  <div class="">
    <div class="h-screen relative w-full fade-in">
      <img
        class="fixed top-0 h-full w-full inset-0 object-cover fade-in saturate-150"
        src="https://images.unsplash.com/photo-1484589065579-248aad0d8b13?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1920&q="
        alt=""
      />

      <div
        class="flex relative justify-center h-full items-center z-10 text-white overflow-hidden"
      >
        <div class="xl:p-32">
          <h1 class="xl:text-[16rem] text-8xl tnr">Gallery</h1>
        </div>
      </div>
    </div>

    <div class="h-screen bg-amber-100 relative">
      <corner-borders></corner-borders>
    </div>
  </div>
</template>

<script>
import CornerBorders from '~/components/CornerBorders.vue'
export default {
  components: { CornerBorders },
}
</script>

<style lang="postcss" scoped>
nav {
  @apply text-white;
}
</style>
