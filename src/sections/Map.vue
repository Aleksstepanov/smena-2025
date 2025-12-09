<template>
  <section class="location">
    <div class="container">
      <h3>Локация</h3>
      <iframe
        src="https://yandex.ru/maps/49/penza/?ll=44.971892%2C53.186387&mode=routes&rtext=~53.184285%2C44.967675&rtt=comparison&ruri=~ymapsbm1%3A%2F%2Forg%3Foid%3D82712461092&utm_source=main_stripe_big&z=15.96"
        width="100%"
        height="300"
        frameborder="0"
      ></iframe>
      <p>
        Как добраться: от ж/д вокзала на автобусе №5, остановка «Библиотека им.
        Лермонтова»
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: "LocationSection",
};
</script>

<style scoped>
.location iframe {
  border: 1px solid var(--bright-blue);
  border-radius: 8px;
}

.location p {
  margin-top: 20px;
  color: white;
  background-color: black;
}
</style>
