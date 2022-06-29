<template>
  <div class="">
    <nuxt-link
      to="/"
      class="fixed top-4 left-4 tnr dark:text-white text-4xl font-bold text-gray-900 z-20"
      >&#8610;</nuxt-link
    >
    <div class="h-screen relative w-full fade-in overflow-hidden">
      <div class="inset-0 filter blur fixed top-0">
        <div class="opacity-25" style="column-gap: 0px; column-count: 6">
          <div v-for="(img, i) in images" :key="i" class="break-inside">
            <img class="object-cover" :src="img" alt="" />
          </div>
        </div>
      </div>

      <div
        class="flex relative justify-center h-full items-center z-10 text-white overflow-hidden"
      >
        <div class="xl:p-32">
          <h1 class="xl:text-[16rem] text-8xl tnr">Gallery</h1>
        </div>
      </div>
    </div>

    <div class="relative bg-amber-50 dark:bg-gray-900 overflow-hidden">
      <div class="container mx-auto my-8 px-4">
        <div class="box-border h-full mx-auto md:masonry break-inside">
          <div
            v-for="(img, i) in images"
            :key="i"
            class="masonry-item break-inside"
            @click="open = !open"
          >
            <masonry-image v-on:details-open="handleDetailsState" :img="img">
            </masonry-image>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CornerBorders from '~/components/CornerBorders.vue'
import MasonryImage from '~/components/MasonryImage.vue'
export default {
  components: { CornerBorders, MasonryImage },
  data() {
    return {
      images: [
        'https://images.unsplash.com/photo-1573658070990-e4c084b95cc5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1160&q=80',
        'https://images.unsplash.com/photo-1598963253993-d215fc582df6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
        'https://images.unsplash.com/flagged/photo-1563296412-742dfbae0afe?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1581661701347-6e695689365b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=776&q=80',
        'https://images.unsplash.com/flagged/photo-1569517282304-d1e2baf737e4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1573658070990-e4c084b95cc5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1160&q=80',
        'https://images.unsplash.com/photo-1605496240272-176f7d1d6158?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1598963253993-d215fc582df6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
        'https://images.unsplash.com/photo-1581661701347-6e695689365b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=776&q=80',
        'https://images.unsplash.com/flagged/photo-1563296412-742dfbae0afe?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1598963253993-d215fc582df6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
        'https://images.unsplash.com/flagged/photo-1569517282304-d1e2baf737e4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1605496240272-176f7d1d6158?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/flagged/photo-1563296412-742dfbae0afe?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1573658070990-e4c084b95cc5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1160&q=80',
        'https://images.unsplash.com/photo-1605496240272-176f7d1d6158?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        'https://images.unsplash.com/photo-1581661701347-6e695689365b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=776&q=80',
        'https://images.unsplash.com/flagged/photo-1569517282304-d1e2baf737e4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
      ],
      open: false,
    }
  },
  methods: {
    handleDetailsState(state) {
      this.open = state
    },
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

.test {
  animation-name: slide-down;
  animation-duration: 20s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

@keyframes slide-down {
  0% {
    transform: translateY(0px);
  }
  100% {
    transform: translateY(100vh);
  }
}
</style>
