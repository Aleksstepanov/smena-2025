<template>
  <section class="faq">
    <div class="container">
      <h2 class="animate-fade">FAQ</h2>
      <details class="animate-fade" v-for="(item, index) in faqItems" :key="index">
        <summary>{{ item.question }}</summary>
        <p>{{ item.answer }}</p>
      </details>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FaqSection',
  data() {
    return {
      faqItems: [
        {
          question: 'Когда начнётся конференция?',
          answer: '15 июня 2026 года.',
        },
        {
          question: 'Сколько стоит билет?',
          answer: 'От 5 000 рублей.',
        },
        {
          question: 'Где пройдёт мероприятие?',
          answer: 'Москва, ул. Примерная, 123. Ближайшее метро — «Примерное», 5 минут пешком.',
        },
        {
          question: 'Можно ли получить счёт для юрлица?',
          answer:
            'Да, отправьте запрос на почту info@secon2026.ru — мы выставим счёт с необходимыми документами.',
        },
        {
          question: 'Есть ли онлайн‑участие?',
          answer: 'Нет, конференция проводится только в очном формате.',
        },
      ],
    }
  },
}
</script>

<style scoped>
.faq {
  font-family: 'Space Grotesk', sans-serif;
  line-height: 1.6;
  color: white;
  background-color: #000000;
  padding: 20px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

/* Гарантируем вертикальное расположение */
details {
  display: block;
  margin-bottom: 16px; /* Отступ между элементами */
}

summary {
  cursor: pointer;
  font-weight: 500;
  padding: 12px 0;
}

p {
  margin: 12px 0 16px;
  padding-left: 8px;
}

/* Анимация появления */
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
