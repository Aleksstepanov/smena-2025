<template>
  <section class="section">
    <slot />
  </section>
</template>

<style scoped>
.section {
  padding: 80px 0; /* базовые вертикальные отступы */
}

@media (max-width: 768px) {
  .section {
    padding: 50px 0;
  }
}
</style>
