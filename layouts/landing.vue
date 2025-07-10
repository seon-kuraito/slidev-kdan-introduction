<script setup lang="ts"></script>

<template>
  <main class="wrapper background">
    <hgroup class="heading">
      <h class="title">
        <slot name="heading-title" />
      </h>
      <p class="description">
        <slot name="heading-description" />
      </p>
    </hgroup>
    <section>
      <img
        class="image"
        src="/images/img-vertical-white.svg"
        alt="img-vertical-white"
      >
    </section>
  </main>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.background {
  background-color: transparent;
  background-image: url('/images/img-landing-decoration.svg');
  background-size: auto 480px;
  background-repeat: no-repeat;
  background-position: center;
}

.heading{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  width: 100%;
  margin-top: 80px;

  .title {
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 600;
    font-size: 56px;
    color: #ffffff;
  }

  .description {
    font-family: 'Allumi Std', sans-serif;
    font-weight: 600;
    font-size: 24px;
    color: #ffffff;
  }
}

.image {
  display: block;
  width: 120px;
  height: 120px;
}
</style>
