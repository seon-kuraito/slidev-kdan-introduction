<script setup lang="ts"></script>

<template>
  <main class="wrapper">
    <hgroup class="heading">
      <slot name="heading-title" />
      <slot
        v-html="html"
        name="heading-description"
      />
    </hgroup>
    <section class="cols">
      <div class="col">
        <slot name="left-image" />
      </div>
      <div class="col">
        <slot name="right-image" />
      </div>
    </section>
    <section class="row">
      <slot name="external-link" />
    </section>
  </main>
</template>

<style scoped>
.wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;
  width: 100%;
  height: 100%;
  padding: 24px 16px;
}

.heading {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  width: 100%;
}

.cols {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  margin-bottom: 24px;
}

.col {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  width: 440px;
}
</style>
