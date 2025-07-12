<script setup lang="ts"></script>

<template>
  <main class="wrapper">
    <img
      class="decoration1"
      src="/images/img-qa-decoration-1.svg"
      alt="img-qa-decoration-1"
    >
    <img
      class="decoration2"
      src="/images/img-qa-decoration-2.svg"
      alt="img-qa-decoration-2"
    >
    <img
      class="decoration3"
      src="/images/img-qa-decoration-3.svg"
      alt="img-qa-decoration-3"
    >
    <img
      class="decoration4"
      src="/images/img-qa-decoration-4.svg"
      alt="img-qa-decoration-4"
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
  align-items: center;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.decoration1 {
  position: absolute;
  width: 210px;
  height: 170px;
  top: 0;
  left: 0;
}

.decoration2 {
  position: absolute;
  width: 210px;
  height: 170px;
  top: 0;
  right: 0;
}

.decoration3 {
  position: absolute;
  width: 210px;
  height: 256px;
  bottom: 0;
  left: 0;
}

.decoration4 {
  position: absolute;
  width: 210px;
  height: 256px;
  bottom: 0;
  right: 0;
}

.heading {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
  width: fit-content;
  margin-top: 120px;

  .title {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 40px;
    line-height: 1.25;
    text-align: center;
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
