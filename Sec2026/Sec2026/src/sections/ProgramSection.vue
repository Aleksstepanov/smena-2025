<template>
  <section class="event-program">
    <div class="container">
      <div class="program-section">
        <h2 class="program-title">Программа мероприятия</h2>

        <div class="program-days">
          <div class="program-day" v-for="day in program" :key="day.id">
            <div class="day-header">
              <h3 class="day-title">{{ day.title }}</h3>
              <div class="day-date">{{ day.date }}</div>
            </div>

            <div class="day-events">
              <div
                class="event-item"
                v-for="event in day.events"
                :key="event.id"
                :class="{ highlight: event.highlight }"
              >
                <div class="event-time">{{ event.time }}</div>
                <div class="event-name">{{ event.name }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const program = ref([
  {
    id: 1,
    title: 'День 1',
    date: '1.02.2026',
    events: [
      { id: 1, time: '09:00 - 10:00', name: 'Регистрация участников', highlight: false },
      { id: 2, time: '10:00 - 10:30', name: 'Торжественное открытие мероприятия', highlight: true },
      { id: 3, time: '10:30 - 12:00', name: 'Нетворкинг-сессия', highlight: false },
      { id: 4, time: '12:00 - 17:00', name: 'Основные доклады и выступления', highlight: true },
    ],
  },
  {
    id: 2,
    title: 'День 2',
    date: '2.02.2026',
    events: [
      { id: 5, time: '09:30 - 12:30', name: 'Питч-сессии инновационных проектов', highlight: true },
      { id: 6, time: '12:30 - 15:30', name: 'Практические воркшопы', highlight: false },
      { id: 7, time: '15:30 - 16:00', name: 'Закрытие мероприятия', highlight: true },
      { id: 8, time: '16:00 - 16:30', name: 'Подведение итогов и награждение', highlight: false },
    ],
  },
])
</script>

<style scoped>
/* Основные стили */
.event-program {
  padding: 100px 20px;
  background: #000;
  position: relative;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
}

/* Заголовок */
.program-title {
  font-size: 64px;
  font-weight: 800;
  color: #ffffff;
  text-align: center;
  margin-bottom: 60px;
}

/* Сетка дней */
.program-days {
  display: flex;
  gap: 40px;
  justify-content: center;
}

/* Карточка дня */
.program-day {
  background: #111111;
  border: 1px solid #333333;
  border-radius: 20px;
  overflow: hidden;
  width: 100%;
  max-width: 580px;
  transition: all 0.3s ease;
}

.program-day:hover {
  transform: translateY(-5px);
  border-color: #444444;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

/* Шапка дня */
.day-header {
  background: #1b2f57;
  color: #ffffff;
  padding: 25px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.day-title {
  font-size: 32px;
  font-weight: 700;
}

.day-date {
  font-size: 18px;
  background: rgba(255, 255, 255, 0.1);
  padding: 8px 16px;
  border-radius: 10px;
}

/* События */
.day-events {
  padding: 20px 0;
}

.event-item {
  display: flex;
  padding: 20px 30px;
  border-bottom: 1px solid #222222;
  transition: all 0.3s ease;
}

.event-item:last-child {
  border-bottom: none;
}

.event-item:hover {
  background: rgba(27, 47, 87, 0.1);
}

/* Выделенные события */
.event-item.highlight {
  background: rgba(27, 47, 87, 0.15);
  border-left: 4px solid #1b2f57;
}

.event-time {
  font-weight: 600;
  color: #568dfc;
  min-width: 200px;
  font-size: 18px;
}

.event-name {
  color: #ffffff;
  font-weight: 500;
  font-size: 18px;
}

/* Анимации */
.program-day {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.program-day:nth-child(1) {
  animation-delay: 0.2s;
}

.program-day:nth-child(2) {
  animation-delay: 0.4s;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Адаптивность */
@media (max-width: 1024px) {
  .program-days {
    flex-direction: column;
    align-items: center;
  }
  
  .program-day {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .event-program {
    padding: 60px 20px;
  }

  .program-title {
    font-size: 48px;
    margin-bottom: 40px;
  }

  .day-header {
    flex-direction: column;
    gap: 15px;
    text-align: center;
    padding: 20px;
  }

  .day-title {
    font-size: 28px;
  }

  .event-item {
    flex-direction: column;
    gap: 10px;
    padding: 15px 20px;
  }

  .event-time {
    min-width: auto;
    font-size: 16px;
  }

  .event-name {
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .program-title {
    font-size: 36px;
  }

  .day-title {
    font-size: 24px;
  }

  .day-date {
    font-size: 16px;
    padding: 6px 12px;
  }
}
</style>