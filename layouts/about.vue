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
    <hgroup class="heading">
      <h2 class="title">
        <slot
          v-html="html"
          name="heading-title"
        />
      </h2>
      <p class="description">
        <slot
          v-html="html"
          name="heading-description"
        />
      </p>
    </hgroup>
  </main>
</template>

<style scoped>
.wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 40px;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.backgroundImage {
  position: absolute;
  top: 0;
  right: 0;
  width: 468px;
  height: 512px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.heading {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 440px;
  margin: 104px 0 0 24px;

  .title {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 40px;
    line-height: 1.25;
    color: #ffffff;
  }

  .description {
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 300;
    font-size: 24px;
    line-height: 1.5;
    color: #00dc87;
  }
}
</style>
