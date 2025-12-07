<template>
  <section class="hero">
    <div class="hero-content">
      <div class="logo fade-in">SECON</div>

      <h1 class="conference-title fade-in delay-1">SECON 2026</h1>
      <div class="conference-subtitle fade-in delay-2">IT конференция</div>

      <div class="hero-buttons fade-in delay-3">
        <a href="#" class="btn btn-ticket">
          <i class="fas fa-ticket-alt"></i>
          Купить билет
        </a>
        <a href="mailto:info@secon2026.ru" class="btn btn-email">
          <i class="fas fa-envelope"></i>
          Отправить email
        </a>
      </div>

      <div class="event-details fade-in delay-4">
        <div class="date-time">1–2 февраля в 12:00</div>
        <div class="location">
          Пенза, ул. Попова 66 к.1<br />
          Центр «Ключевский»
        </div>
      </div>

      <div class="countdown-section fade-in delay-5">
        <div class="countdown-title">До начала конференции осталось:</div>

        <div class="timer">
          <div class="time-block">
            <div class="time-value">{{ days }}</div>
            <div class="time-label">Дни</div>
          </div>

          <div class="time-block">
            <div class="time-value">{{ hours }}</div>
            <div class="time-label">Часы</div>
          </div>

          <div class="time-block">
            <div class="time-value">{{ minutes }}</div>
            <div class="time-label">Минуты</div>
          </div>

          <div class="time-block">
            <div class="time-value">{{ seconds }}</div>
            <div class="time-label">Секунды</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const days = ref('00')
const hours = ref('00')
const minutes = ref('00')
const seconds = ref('00')

const conferenceDate = new Date('February 1, 2026 12:00:00').getTime()

function updateCountdown() {
  const now = new Date().getTime()
  const timeLeft = conferenceDate - now

  if (timeLeft <= 0) {
    days.value = '00'
    hours.value = '00'
    minutes.value = '00'
    seconds.value = '00'
    return
  }

  const d = Math.floor(timeLeft / (1000 * 60 * 60 * 24))
  const h = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
  const m = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60))
  const s = Math.floor((timeLeft % (1000 * 60)) / 1000)

  days.value = d.toString().padStart(2, '0')
  hours.value = h.toString().padStart(2, '0')
  minutes.value = m.toString().padStart(2, '0')
  seconds.value = s.toString().padStart(2, '0')
}

onMounted(() => {
  updateCountdown()
  setInterval(updateCountdown, 1000)
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
  background:
    radial-gradient(circle at 20% 30%, rgba(var(--primary-rgb), 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(var(--accent-purple-rgb), 0.1) 0%, transparent 50%),
    linear-gradient(145deg, color-mix(in srgb, var(--background) 90%, black), var(--background));
  position: relative;
  overflow: hidden;
  text-align: center;
}

.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%232E3BFF' fill-opacity='0.05' fill-rule='evenodd'/%3E%3C/svg%3E"),
    linear-gradient(145deg, color-mix(in srgb, var(--background) 90%, black), var(--background));
  z-index: 0;
  opacity: 0.5;
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 1200px;
  margin: 0 auto;
}

.logo {
  font-size: 1.2rem;
  color: var(--accent-light);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 30px;
  font-weight: 600;
}

.conference-title {
  font-size: 4.5rem;
  font-weight: 900;
  background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  margin-bottom: 20px;
}

.conference-subtitle {
  font-size: 2.2rem;
  color: var(--accent-light);
  margin-bottom: 40px;
  opacity: 0.9;
}

.hero-buttons {
  display: flex;
  justify-content: center;
  gap: var(--space);
  flex-wrap: wrap;
  margin-bottom: 40px;
}

.btn {
  padding: 20px 50px;
  font-size: 1.3rem;
  font-weight: 600;
  border-radius: var(--radius);
  position: relative;
  overflow: hidden;
  display: inline-flex;
  align-items: center;
  gap: 12px;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.btn::before {
  content: '';
  position: absolute;
  inset: 0;
  left: -100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.7s ease;
}

.btn:hover::before {
  left: 100%;
}

.btn-ticket {
  background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
  color: var(--text);
}

.btn-ticket:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(46, 59, 255, 0.4);
}

.btn-email {
  background: transparent;
  border: 2px solid var(--secondary);
  color: var(--accent-light);
}

.btn-email:hover {
  background: rgba(50, 76, 136, 0.1);
  transform: translateY(-3px);
  border-color: var(--accent-light);
}

.event-details {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 60px auto 0;
  padding: 40px;
  background: rgba(0, 36, 71, 0.7);
  border-radius: calc(var(--radius) * 2);
  border: 1px solid var(--secondary);
  max-width: 800px;
}

.date-time,
.location {
  font-size: 1.8rem;
  color: var(--accent-light);
  line-height: 1.4;
}

.countdown-section {
  margin-top: 60px;
}

.countdown-title {
  font-size: 1.5rem;
  color: var(--accent-light);
  margin-bottom: 30px;
  opacity: 0.9;
}

.timer {
  display: flex;
  justify-content: center;
  gap: calc(var(--space) * 2);
  flex-wrap: wrap;
}

.time-block {
  background: rgba(255, 255, 255, 0.05);
  padding: 25px 20px;
  border-radius: calc(var(--radius) * 2);
  border: 1px solid rgba(255, 255, 255, 0.1);
  min-width: 140px;
}

.time-value {
  font-size: 4.5rem;
  font-weight: 900;
  background: linear-gradient(90deg, var(--accent-purple), var(--accent-light));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  line-height: 1;
}

.time-label {
  font-size: 1.4rem;
  color: var(--gray-medium);
  margin-top: 10px;
}

/* Анимации */
.fade-in {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.delay-1 {
  animation-delay: 0.2s;
}
.delay-2 {
  animation-delay: 0.4s;
}
.delay-3 {
  animation-delay: 0.6s;
}
.delay-4 {
  animation-delay: 0.8s;
}
.delay-5 {
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
  .conference-title {
    font-size: 3rem;
  }

  .conference-subtitle {
    font-size: 1.8rem;
  }

  .event-details {
    flex-direction: column;
    gap: 20px;
    text-align: center;
    padding: 30px 20px;
  }

  .date-time,
  .location {
    font-size: 1.4rem;
  }

  .time-value {
    font-size: 3.5rem;
  }

  .timer {
    gap: var(--space);
  }

  .time-block {
    min-width: 100px;
    padding: 20px 15px;
  }

  .btn {
    padding: 15px 30px;
    font-size: 1.1rem;
  }
}

@media (max-width: 480px) {
  .conference-title {
    font-size: 2.5rem;
  }

  .conference-subtitle {
    font-size: 1.5rem;
  }

  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }

  .btn {
    width: 100%;
    max-width: 280px;
    justify-content: center;
  }
}
</style>
