<template>
  <div class="relative group">
    <img
      @click="open = !open"
      loading="lazy"
      class="object-cover w-full h-full rounded-md shadow-lg"
      :src="img"
    />

    <div
      @click="open = false"
      v-if="open"
      class="fixed inset-0 bg-black bg-opacity-90 backdrop-blur-sm z-50"
    >
      <div class="flex items-center h-full justify-center">
        <div class="p-4 h-full">
          <div
            class="flex lg:flex-nowrap items-center h-full flex-wrap text-gray-100 overflow-auto"
          >
            <img
              class="object-cover fade-in h-[75vh] rounded-md shadow-lg"
              :src="img"
              alt=""
            />
            <div class="w-full pl-4 pt-4 max-w-xs">
              <h3 class="text-xl tnr">Image Caption</h3>

              <p class="mt-4 text-sm">
                Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                diam nonumy eirmod tempor invidunt ut labore et dolore magna
                aliquyam erat, sed diam voluptua. At vero eos et accusam et
                justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea
                takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum
                dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
                eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
                sed diam voluptua.
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
}
</script>
