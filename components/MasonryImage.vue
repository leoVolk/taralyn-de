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
        class="flex items-center xl:max-w-screen-sm w-full h-full justify-center"
      >
        <div class="p-4 fade-in lg:h-auto h-full">
          <div
            class="px-4 overflow-auto relative h-full lg:h-auto dark:bg-gray-900 bg-amber-50 text-gray-900 dark:text-gray-100 rounded-md"
          >
            <h3
              class="text-2xl py-4 font-medium dark:bg-gray-900 bg-amber-50 sticky top-0 transition-all duration-300"
            >
              Image Caption
            </h3>
            <img
              class="object-contain rounded-md shadow-lg"
              :src="img"
              alt=""
            />

            <div>
              <p class="my-4">
                Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                diam nonumy eirmod tempor invidunt ut labore et dolore magna
                aliquyam erat, sed diam voluptua. At vero eos et accusam et
                justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea
                takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum
                dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
                eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
                sed diam voluptua. At vero eos et accusam et justo duo dolores
                et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus
                est Lorem ipsum dolor sit amet.
              </p>
            </div>
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
