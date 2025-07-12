<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  frontmatter: Record<string, any>
}>()

const backgroundImage = computed(() => props.frontmatter.image)
</script>

<template>
  <main class="wrapper">
    <div
      class="backgroundImage"
      :style="{ backgroundImage: `url('${backgroundImage}')` }"
    >
    </div>
    <img
      class="decoration2"
      src="/images/img-glance-decoration-2.svg"
      alt="img-glance-decoration-2"
    >
    <img
      class="decoration4"
      src="/images/img-glance-decoration-4.svg"
      alt="img-glance-decoration-4"
    >
  </main>
</template>

<style scoped>
.wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.backgroundImage {
  position: relative;
  z-index: 1;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.decoration2 {
  position: absolute;
  z-index: 0;
  top: -72px;
  left: 438px;
  width: 244px;
  height: 166px;
}

.decoration4 {
  position: absolute;
  z-index: 0;
  bottom: 0;
  left: 0;
  width: 358px;
  height: 336px;
}
</style>
