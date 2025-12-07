<template>
  <section class="event-fragment">
    <div class="container">
      <div class="section-header">
        <div class="section-label">ПРОГРАММА</div>
        <h2 class="section-title">Что вас ждёт</h2>
        <p class="section-subtitle">
          Присоединяйтесь к нашему мероприятию, чтобы узнать о последних тенденциях и инновациях в
          отрасли
        </p>
      </div>

      <div class="features">
        <div class="feature" v-for="feature in features" :key="feature.id">
          <div class="feature-icon">{{ feature.icon }}</div>
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-desc">{{ feature.desc }}</p>
        </div>
      </div>

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

const features = ref([
  {
    id: 1,
    icon: '🎤',
    title: 'Выступления ведущих экспертов',
    desc: 'Узнайте от лидеров отрасли о последних трендах и будущих направлениях развития',
  },
  {
    id: 2,
    icon: '🚀',
    title: 'Презентации инновационных проектов',
    desc: 'Откройте для себя передовые разработки и технологические решения',
  },
  {
    id: 3,
    icon: '🤝',
    title: 'Обмен опытом и знаниями',
    desc: 'Возможность обсудить идеи и поделиться опытом с коллегами',
  },
])

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
.event-fragment {
  padding: 100px 20px;
  background: linear-gradient(
    180deg,
    var(--background),
    color-mix(in srgb, var(--background) 95%, black)
  );
  position: relative;
  overflow: hidden;
}

.event-fragment::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(circle at 10% 20%, rgba(46, 59, 255, 0.05) 0%, transparent 40%),
    radial-gradient(circle at 90% 80%, rgba(129, 118, 237, 0.05) 0%, transparent 40%);
  z-index: 1;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.section-header {
  text-align: center;
  margin-bottom: 80px;
}

.section-label {
  font-size: 1rem;
  color: var(--accent-light);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 20px;
  font-weight: 600;
}

.section-title {
  font-size: 3.5rem;
  font-weight: 900;
  background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  margin-bottom: 20px;
}

.section-subtitle {
  font-size: 1.5rem;
  color: var(--accent-light);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
  opacity: 0.9;
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: calc(var(--space) * 2);
  margin-bottom: 100px;
}

.feature {
  background: rgba(0, 36, 71, 0.7);
  border: 1px solid var(--secondary);
  border-radius: calc(var(--radius) * 2);
  padding: calc(var(--space) * 2);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.feature:hover {
  transform: translateY(-10px);
  border-color: var(--accent-light);
  box-shadow: 0 20px 40px rgba(59, 213, 255, 0.1);
}

.feature::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
  opacity: 0;
  transition: opacity 0.3s ease;
}

.feature:hover::before {
  opacity: 1;
}

.feature-icon {
  font-size: 3rem;
  margin-bottom: 25px;
}

.feature-title {
  font-size: 1.5rem;
  color: var(--text);
  margin-bottom: 15px;
  font-weight: 600;
}

.feature-desc {
  color: var(--gray-medium);
  line-height: 1.6;
  font-size: 1.1rem;
}

.program-section {
  margin-top: 80px;
}

.program-title {
  font-size: 2.5rem;
  color: var(--text);
  text-align: center;
  margin-bottom: 50px;
  font-weight: 700;
}

.program-days {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: calc(var(--space) * 3);
}

.program-day {
  background: rgba(0, 36, 71, 0.7);
  border: 1px solid var(--secondary);
  border-radius: calc(var(--radius) * 2);
  overflow: hidden;
  transition: all 0.3s ease;
}

.program-day:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(46, 59, 255, 0.1);
  border-color: var(--accent-light);
}

.day-header {
  background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
  color: var(--text);
  padding: 25px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.day-title {
  font-size: 1.8rem;
  font-weight: 700;
}

.day-date {
  font-size: 1.2rem;
  opacity: 0.9;
  background: rgba(255, 255, 255, 0.1);
  padding: 5px 15px;
  border-radius: var(--radius);
}

.day-events {
  padding: 20px 0;
}

.event-item {
  display: flex;
  padding: 20px 30px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.event-item:last-child {
  border-bottom: none;
}

.event-item:hover {
  background: rgba(59, 213, 255, 0.05);
}

.event-item.highlight {
  background: linear-gradient(90deg, rgba(46, 59, 255, 0.1), transparent);
  border-left: 3px solid var(--accent-light);
}

.event-time {
  font-weight: 600;
  color: var(--accent-light);
  min-width: 140px;
  font-size: 1.1rem;
}

.event-name {
  color: var(--text);
  font-weight: 500;
  font-size: 1.2rem;
}

/* Анимации для появления элементов */
.feature,
.program-day {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.feature:nth-child(1) {
  animation-delay: 0.2s;
}
.feature:nth-child(2) {
  animation-delay: 0.4s;
}
.feature:nth-child(3) {
  animation-delay: 0.6s;
}
.program-day:nth-child(1) {
  animation-delay: 0.8s;
}
.program-day:nth-child(2) {
  animation-delay: 1s;
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

/* Адаптив */
@media (max-width: 768px) {
  .event-fragment {
    padding: 60px 20px;
  }

  .section-title {
    font-size: 2.5rem;
  }

  .section-subtitle {
    font-size: 1.2rem;
  }

  .features {
    grid-template-columns: 1fr;
    gap: var(--space);
  }

  .program-days {
    grid-template-columns: 1fr;
    gap: calc(var(--space) * 2);
  }

  .day-header {
    flex-direction: column;
    gap: 10px;
    text-align: center;
    padding: 20px;
  }

  .event-item {
    flex-direction: column;
    gap: 10px;
    padding: 15px 20px;
  }

  .event-time {
    min-width: auto;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }

  .feature {
    padding: calc(var(--space) * 1.5);
  }

  .feature-title {
    font-size: 1.3rem;
  }
}
</style>
