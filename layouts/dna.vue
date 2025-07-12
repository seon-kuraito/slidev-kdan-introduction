<script setup lang="ts">
import { ref, computed } from 'vue'

const agility = '/images/img-agility.webp'
const inclusion = '/images/img-inclusion.webp'
const reliability = '/images/img-reliability.webp'

const currentImageSrc = ref(agility)

const currentImageAlt = computed(() => currentImageSrc.value.replace('/images/', '').replace('.webp', ''))

const isAgility = computed(() => currentImageSrc.value === agility)
const isInclusion = computed(() => currentImageSrc.value === inclusion)
const isReliability = computed(() => currentImageSrc.value === reliability)

const switchImage = (imageSrc: string) => {
  if (currentImageSrc.value === imageSrc) {
    return
  }

  currentImageSrc.value = imageSrc
}
</script>

<template>
  <main class="wrapper">
    <hgroup class="heading">
      <slot name="heading-title" />
    </hgroup>
    <section class="cols">
      <div class="col">
        <img
          class="image"
          :src="currentImageSrc"
          :alt="currentImageAlt"
        >
      </div>
      <div class="col">
        <ul class="tabs">
          <li
            class="tab"
            :class="{ expanded: isAgility }"
            @click="switchImage(agility)"
          >
            <img
              class="icon"
              src="/images/ic-agility.webp"
              alt="ic-agility"
            >
            <h3 class="title">
              <slot name="agility-title" />
            </h3>
            <img
              class="icon"  
              src="/images/ic-arrow.svg"
              alt="ic-arrow"
            >
            <p
              class="description"
              v-show="isAgility"
            >
              <slot name="agility-description" />
            </p>
          </li>
          <li
            class="tab"
            :class="{ expanded: isInclusion }"
            @click="switchImage(inclusion)"
          >
            <img
              class="icon"
              src="/images/ic-inclusion.webp"
              alt="ic-inclusion"
            >
            <h3 class="title">
              <slot name="inclusion-title" />
            </h3>
            <img
              class="icon"  
              src="/images/ic-arrow.svg"
              alt="ic-arrow"
            >
            <p
              class="description"
              v-show="isInclusion"
            >
              <slot name="inclusion-description" />
            </p>
          </li>
          <li
            class="tab"
            :class="{ expanded: isReliability }"
            @click="switchImage(reliability)"
          >
            <img
              class="icon"
              src="/images/ic-reliability.webp"
              alt="ic-reliability"
            >
            <h3 class="title">
              <slot name="reliability-title" />
            </h3>
            <img
              class="icon"  
              src="/images/ic-arrow.svg"
              alt="ic-arrow"
            >
            <p
              class="description"
              v-show="isReliability"
            >
              <slot name="reliability-description" />
            </p>
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.heading{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  width: 100%;

  .title {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 36px;
    color: #ffffff;
  }
}

.cols {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 64px;
}

.col {
  width: 400px;
  height: 400px;
}

.image {
  display: block;
  width: 400px;
  height: 400px;
}

.tabs {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  height: 100%;
}

.tab {
  display: flex;
  position: relative;
  flex-wrap: wrap;
  align-items: center;
  gap: 8px 0;
  width: 100%;
  height: fit-content;
  padding: 24px 24px 24px 36px;
  border-radius: 8px;
  box-shadow: 0 0 12px 0 rgba(0, 0, 0, 0.1);
  background-color: #0d3841;

  .icon {
    display: block;
    width: 40px;
    height: 40px;
  }

  .title {
    flex-grow: 1;
    margin-left: 24px;
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 600;
    font-size: 28px;
    color: #ffffff;
  }

  .description {
    flex-grow: 1;
    margin: 0 40px 0 64px;
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 400;
    font-size: 16px;
    color: #ffffff;
    opacity: 0.8;
  }
}

.tab:not(.expanded) {
  cursor: pointer;
}

.tab.expanded::before {
  content: '';
  position: absolute;
  left: 0;
  width: 12px;
  height: 100%;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
  background-color: #00dc87;
}

.tab.expanded img[alt="ic-arrow"] {
  transform: rotate(180deg);
  transition: transform 0.3s ease;
}
</style>
