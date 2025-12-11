<template>
  <div class="container">
    <slot />
  </div>
</template>

<style scoped>
/* Базовые настройки контейнера */

.container {
  max-width: 1280px;   /* Основная ширина контента */
  margin: 0 auto;      /* Центровка на десктопе */
  padding: 0 20px;     /* Мобильные отступы по бокам */

  width: 100%;
}

/* ПЛАНШЕТЫ */
@media (min-width: 768px) {
  .container {
    padding: 0 32px;
    max-width: 1440px; /* на планшете центрирование + немного шире */
  }
}

/* НОУТБУКИ И ДЕСКТОП */
@media (min-width: 1024px) {
  .container {
    padding: 0 48px;
    max-width: 1440px;
  }
}

/* ШИРОКИЕ ЭКРАНЫ — 4K */
@media (min-width: 1600px) {
  .container {
    max-width: 1600px;
  }
}
</style>