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
      class="fixed top-0 inset-0 bg-black bg-opacity-90 backdrop-blur-sm z-50"
    >
      <div class="flex items-center h-full justify-center">
        <div class="p-4 h-full">
          <div
            class="flex lg:flex-nowrap lg:items-center h-full flex-wrap text-gray-100 overflow-auto"
          >
            <img
              class="lg:object-cover object-contain fade-in lg:h-[75vh] rounded-md shadow-lg"
              :src="img"
              alt=""
            />
          </div>
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
