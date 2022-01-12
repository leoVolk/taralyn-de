<template>
  <div class="relative">
    <img
      @click="open = !open"
      loading="lazy"
      class="object-cover w-full h-full rounded-md shadow-lg"
      :src="img"
    />

    <div
      @click="open = false"
      v-if="open"
      class="fixed inset-0 bg-black bg-opacity-75 z-50"
    >
      <div class="flex h-full items-center justify-center">
        <div class="px-4">
          <img
            class="object-cover fade-in h-[75vh] rounded-md shadow-lg"
            :src="img"
            alt=""
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['img'],
  data() {
    return {
      open: false,
    }
  },
}
</script>
