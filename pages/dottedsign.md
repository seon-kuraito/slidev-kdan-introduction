---
layout: solutions
transition: fade-out
glow: bottom-right
---

<script setup lang="ts">
import { ref } from 'vue'

const firstImageSrc = '/images/img-solutions-dottedsign-1.png'
const firstImageAlt = 'img-solutions-dottedsign-1'

const secondImageSrc = '/images/img-solutions-dottedsign-2.png'
const secondImageAlt = 'img-solutions-dottedsign-2'

const isFullscreen = ref<boolean>(false)
const fullscreenImageSrc = ref<string>('')

const openFullscreen = (imageSrc: string): void => {
  fullscreenImageSrc.value = imageSrc
  isFullscreen.value = true
  document.body.style.overflow = 'hidden'
}

const closeFullscreen = (): void => {
  isFullscreen.value = false
  fullscreenImageSrc.value = ''
  document.body.style.overflow = 'auto'
}
</script>

::heading-title::

<h2>
  DottedSign
</h2>

::heading-description::

<p>
  電子簽名流程服務，包涵 SaaS、客製化 API 等解決方案，符合台灣《電子簽章法》，<br/>打造安心數位化工作流程。
</p>

::left-image::

<img
  :src="firstImageSrc"
  :alt="firstImageAlt"
  @click="openFullscreen(firstImageSrc)"
/>

::right-image::

<img
  :src="secondImageSrc"
  :alt="secondImageAlt"
  @click="openFullscreen(secondImageSrc)"
/>

::external-link::

<a href="https://www.dottedsign.com" target="_blank">
  Your Business Growth Starts with DottedSign ↗︎
</a>

<div
  v-if="isFullscreen"
  class="fullscreen-overlay"
  @click="closeFullscreen"
>
  <img
    :src="fullscreenImageSrc"
    class="fullscreen-image"
    @click.stop
  />
  <button
    class="close-button"
    @click="closeFullscreen"
  >
    ✕
  </button>
</div>

<style scoped>
h2 {
  font-family: 'Allumi Std', sans-serif;
  font-weight: 600;
  font-size: 36px;
  color: transparent;
  background: linear-gradient(to right, #5b58f2 0%, #008cff 100%);
  background-clip: text;
}

p {
  font-family: 'Noto Sans TC', sans-serif;
  font-weight: 300;
  font-size: 20px;
  text-align: center;
  line-height: 1.5;
  color: #ffffff;
  opacity: 0.8;
}

img {
  display: block;
  border-radius: 4px;
  box-shadow: 0 0 12px 0 rgba(0, 0, 0, 0.25);
  transition: all 0.2s ease-in-out;
  cursor: pointer;

  &:hover {
    scale: 1.01;
  }
}

.fullscreen-overlay {
  position: fixed;
  z-index: 9999;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  cursor: pointer;
}

.fullscreen-image {
  position: absolute;
  width: 80%;
  height: 80%;
  cursor: default;

  &:hover {
    scale: none;
  }
}

.close-button {
  position: absolute;
  top: 20px;
  right: 20px;
  padding: 8px 12px;
  font-size: 24px;
  cursor: pointer;
}

a {
  font-family: 'Allumi Std', sans-serif;
  font-weight: 600;
  font-size: 12px;
  color: #ffffff;

  &:hover {
    text-decoration: underline;
  }
}
</style>

<!--
接著，也是大家最熟悉、最廣為人知的電子簽名「唯一首選」—— DottedSign 點點簽。

點點簽題供「零阻力電子簽名」，包涵 SaaS、API 客製化以及私有化部署等解決方案。

我們的目的：幫助企業以更快速、安全且合規的方式完成文件簽署，縮短流程週期並落實 ESG。
-->
