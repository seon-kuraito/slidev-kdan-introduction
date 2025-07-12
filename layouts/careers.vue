<script setup lang="ts"></script>

<template>
  <main class="wrapper">
    <hgroup class="heading">
      <h2 class="title">
        <slot name="heading-title" />
      </h2>
    </hgroup>
    <section class="cols">
      <div class="col">
        <h3 class="title">
          <slot name="left-title" />
        </h3>
        <img
          class="image"
          src="/images/img-careers-1.png"
          alt="img-careers-1"
        >
      </div>
      <div class="col">
        <h3 class="title">
          <slot name="right-title" />
        </h3>
        <img
          class="image"
          src="/images/img-careers-2.png"
          alt="img-careers-2"
        >
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
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  width: 400px;
  height: 400px;

  .image {
    display: block;
    width: 320px;
    height: 320px;
  }

  .title {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 24px;
    color: #00dc87;
  }
}
</style>
