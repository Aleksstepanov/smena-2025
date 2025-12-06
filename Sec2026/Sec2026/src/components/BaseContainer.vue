<template>
  <div class="container">
    <slot />
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  max-width: var(--container-max);
  padding: 0 var(--container-padding);
  margin: 0 auto;
}
</style>
