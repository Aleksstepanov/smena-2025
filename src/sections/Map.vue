<template>
  <section class="location">
    <div class="container">
      <h3 class="title">Локация</h3>
      <iframe
        src="https://yandex.ru/map-widget/v1/?ll=37.6176,55.7558&z=10"
        width="100%"
        height="300"
        frameborder="0"
      ></iframe>
      <p>Как добраться: от ж/д вокзала на автобусе №5, остановка «Библиотека им. Лермонтова»</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'LocationSection',
}
</script>

<style scoped>
.location {
  background-color: #000000;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.title {
  text-align: center;
  margin-bottom: 20px;
  font-size: 48px; /* Увеличенный размер шрифта */
  font-weight: 700; /* Жирное начертание */
  color: white; /* Белый цвет текста */
  letter-spacing: 0.5px; /* Небольшой межбуквенный интервал для лучшей читаемости */
}

.location iframe {
  border: 1px solid var(--bright-blue);
  border-radius: 8px;
  background-color: #000000;
  font-family: 'Space Grotesk', sans-serif;
  margin: 0 auto;
}

.location p {
  margin-top: 20px;
  color: white;
  background-color: #000000;
  text-align: center;
  font-size: 18px; /* Немного увеличили размер текста инструкции */
}
</style>
