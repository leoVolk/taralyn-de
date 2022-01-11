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

    <div class="relative bg-amber-50 dark:bg-gray-900 overflow-hidden">
      <div class="container mx-auto my-8">
        <div class="box-border h-full mx-auto md:masonry break-inside">
          <div
            v-for="(img, i) in images"
            :key="i"
            class="masonry-item break-inside"
          >
            <img
              loading="lazy"
              class="object-cover w-full h-full rounded-md shadow-lg"
              :src="img"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CornerBorders from '~/components/CornerBorders.vue'
export default {
  components: { CornerBorders },
  data() {
    return {
      images: [
        'https://images.unsplash.com/photo-1573658070990-e4c084b95cc5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1160&q=80',
        'https://images.unsplash.com/photo-1598963253993-d215fc582df6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
        'https://images.unsplash.com/flagged/photo-1563296412-742dfbae0afe?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1581661701347-6e695689365b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=776&q=80',
        'https://images.unsplash.com/flagged/photo-1569517282304-d1e2baf737e4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1605496240272-176f7d1d6158?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
      ],
    }
  },
}
</script>

<style lang="postcss" scoped>
nav {
  @apply text-white;
}

.masonry-item {
  @apply mb-4 bg-gray-200 rounded-lg shadow-lg;
}
</style>
