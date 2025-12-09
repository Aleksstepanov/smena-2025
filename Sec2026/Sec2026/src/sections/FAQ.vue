<template>
  <section class="faq">
    <div class="container">
      <h2 class="animate-fade">FAQ</h2>
      <details class="animate-fade">
        <summary>Когда начнётся конференция?</summary>
        <p>15 июня 2026 года.</p>
      </details>
      <details class="animate-fade">
        <summary>Сколько стоит билет?</summary>
        <p>От 5 000 рублей.</p>
      </details>
      <details class="animate-fade">
        <summary>Где пройдёт мероприятие?</summary>
        <p>Москва, ул. Примерная, 123. Ближайшее метро — «Примерное», 5 минут пешком.</p>
      </details>
      <details class="animate-fade">
        <summary>Можно ли получить счёт для юрлица?</summary>
        <p>
          Да, отправьте запрос на почту info@secon2026.ru — мы выставим счёт с необходимыми
          документами.
        </p>
      </details>
      <details class="animate-fade">
        <summary>Есть ли онлайн‑участие?</summary>
        <p>Нет, конференция проводится только в очном формате.</p>
      </details>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FaqSection',
}
</script>

<style scoped>
.faq {
  font-family: 'Space Grotesk', sans-serif;
  line-height: 1.6;
  color: white;
  background-color: #000000;
}

.faq {
  padding: 20px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.animate-fade {
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
