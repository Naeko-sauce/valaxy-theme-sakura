<script lang="ts" setup>
import { computed } from 'vue'
import { useMounted } from '@vueuse/core'
import { useThemeConfig } from '../composables'
import type { Banner } from '../types/index'

const props = defineProps<{
  banner?: Banner
}>()

const themeConfig = useThemeConfig()
const isMounted = useMounted()

const banner = computed(() => props.banner || themeConfig.value.banner)
</script>

<template>
  <header class="sakura-banner <md:px-5">
    <template v-if="isMounted">
      <div class="absolute h-full w-full top-0 overflow-hidden" :class="[banner.style && 'banner-style', banner.style]">
        <slot name="background-display" />

        <slot name="overlay-bar" />
      </div>
      <div z-4>
        <slot name="info-overlay" />
      </div>
    </template>
  </header>
</template>

<style lang="scss">
.sakura-banner {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;

  .banner-style::before {
    content: '';
    position: absolute;
    inset: 0;
    background-attachment: fixed
  }

  .banner-style.filter-dim::before {
    background-color: rgba(0, 0, 0, 0.3)
  }

  .banner-style.filter-grid::before {
    background-image: url("https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/other/grid.png")
  }

  .banner-style.filter-dot::before {
    background-image: url("https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/other/dot.gif");
  }
}
</style>
