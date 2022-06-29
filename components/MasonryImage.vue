<template>
  <div class="relative group">
    <div class="rounded-md dark:bg-gray-700 dark:text-gray-100 shadow-lg">
      <img
        loading="lazy"
        class="object-cover w-full h-full rounded-md"
        :src="img"
        @click="toggleDetail()"
      />
    </div>

    <div
      @click="toggleDetail()"
      v-if="open"
      class="fixed top-0 items-center inset-0 flex justify-center bg-black bg-opacity-90 backdrop-blur-sm z-50 py-8"
    >
      <div
        class="flex items-center xl:max-w-screen-sm w-full h-scren justify-center"
      >
        <div class="p-4 fade-in lg:h-auto h-full">
          <img class="object-contain rounded-md shadow-lg" :src="img" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CornerBorders from './CornerBorders.vue'
export default {
  props: ['img'],
  components: [CornerBorders],
  data() {
    return {
      open: false,
    }
  },
  methods: {
    toggleDetail() {
      this.open = !this.open

      this.$emit('details-open', this.open)
    },
  },
}
</script>
