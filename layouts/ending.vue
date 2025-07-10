<script setup lang="ts"></script>

<template>
  <main class="wrapper">
    <img
      class="decoration1"
      src="/images/img-ending-decoration-1.svg"
      alt="img-ending-decoration-1"
    >
    <img
      class="decoration2"
      src="/images/img-ending-decoration-2.svg"
      alt="img-ending-decoration-2"
    >
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

.decoration1 {
  position: absolute;
  top: 0;
  right: 0;
  width: 400px;
  height: 430px;
}

.decoration2 {
  position: absolute;
  bottom: 74px;
  right: 418px;
  width: 64px;
  height: 64px;
}

.heading {
  display: flex;
  flex-direction: column;
  gap: 40px;
  width: fit-content;
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
