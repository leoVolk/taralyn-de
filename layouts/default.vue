<template>
  <div class="relative min-h-screen">
    <div class="fixed -top-4 -left-14 z-40">
      <div class="switch">
        <input
          v-model="isLight"
          class="scale-[25%]"
          @change="toggleTheme()"
          type="checkbox"
          name="toggle"
        />
        <label class="scale-[25%]" for="toggle">
          <i class="bulb">
            <span class="bulb-center"></span>
            <span class="filament-1"></span>
            <span class="filament-2"></span>
            <span class="reflections">
              <span></span>
            </span>
            <span class="sparks">
              <i class="spark1"></i>
              <i class="spark2"></i>
              <i class="spark3"></i>
              <i class="spark4"></i>
            </span>
          </i>
        </label>
      </div>
    </div>

    <Nuxt></Nuxt>
  </div>
</template>
<script>
import 'animate.css'
export default {
  data() {
    return {
      isLight: false,
    }
  },
  mounted() {
    if (
      localStorage.theme === 'dark' ||
      (!('theme' in localStorage) &&
        window.matchMedia('(prefers-color-scheme: dark)').matches)
    ) {
      document.documentElement.classList.add('dark')
      this.isLight = false
    } else {
      document.documentElement.classList.remove('dark')
      this.isLight = true
    }
  },
  methods: {
    toggleTheme() {
      if (!this.isLight) {
        localStorage.theme = 'dark'
        document.documentElement.classList.add('dark')
      } else {
        localStorage.theme = 'light'
        document.documentElement.classList.remove('dark')
      }
    },
  },
}
</script>

<style lang="postcss"></style>
