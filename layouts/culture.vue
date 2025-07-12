<script setup lang="ts"></script>

<template>
  <main class="wrapper">
    <img
      class="decoration1"
      src="/images/img-culture-decoration-1.svg"
      alt="img-culture-decoration-1"
    >
    <img
      class="decoration2"
      src="/images/img-culture-decoration-2.svg"
      alt="img-culture-decoration-2"
    >
    <section class="cols">
      <div class="col">
        <hgroup class="heading">
          <h2 class="title">
            <slot name="heading-title" />
          </h2>
          <p class="description">
            <slot
              v-html="html"
              name="heading-description"
            />
          </p>
        </hgroup>
      </div>
      <div class="col">
      </div>
    </section>
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

.decoration1 {
  position: absolute;
  right: 184px;
  height: 460px;
  z-index: 1;
}

.decoration2 {
  position: absolute;
  right: 34px;
  height: 460px;
  z-index: 0;
}

.heading{
  display: flex;
  flex-direction: column;
  gap: 56px;
  width: fit-content;
  margin: 104px 0 0 24px;

  .title {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 36px;
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

.cols {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}

.col {
  width: 50%;
  height: 100%;
}
</style>
