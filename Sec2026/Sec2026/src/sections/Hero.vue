<template>
  <section class="hero">
    <div class="hero-content">
      <div class="logo fade-in">SECON</div>

      <h1 class="conference-title fade-in delay-1">SECON 2026</h1>
      <div class="conference-subtitle fade-in delay-2">
        IT конференция
      </div>

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
        <div class="date-time">
          1–2 февраля в 12:00
        </div>
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
import { ref, onMounted } from "vue";

const days = ref("00");
const hours = ref("00");
const minutes = ref("00");
const seconds = ref("00");

const conferenceDate = new Date("February 1, 2026 12:00:00").getTime();

function updateCountdown() {
  const now = new Date().getTime();
  const timeLeft = conferenceDate - now;

  if (timeLeft <= 0) return;

  const d = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
  const h = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  const m = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
  const s = Math.floor((timeLeft % (1000 * 60)) / 1000);

  days.value = d.toString().padStart(2, "0");
  hours.value = h.toString().padStart(2, "0");
  minutes.value = m.toString().padStart(2, "0");
  seconds.value = s.toString().padStart(2, "0");
}

onMounted(() => {
  updateCountdown();
  setInterval(updateCountdown, 1000);

  // включаем анимации
  document.querySelectorAll(".fade-in").forEach((el) => {
    el.style.animationPlayState = "running";
  });
});
</script>

<style scoped>
/* ===== ТВОИ СТИЛИ ПЕРЕНЕСЕНЫ 1 В 1 ===== */

.hero {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
  background: radial-gradient(circle at 20% 30%, rgba(74, 127, 255, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(255, 107, 157, 0.1) 0%, transparent 50%),
    linear-gradient(145deg, #11112a, #0d0d1f);
  position: relative;
  overflow: hidden;
  text-align: center;
}

.hero::before {
  content: "";
  position: absolute;
  inset: 0;
  background: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><path d='M0,0 L100,0 L100,100 Z' fill='%23333355' opacity='0.05'/></svg>");
  background-size: cover;
  z-index: 0;
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 1200px;
}

.logo {
  font-size: 1.2rem;
  color: #8899cc;
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 30px;
  font-weight: 600;
}

.conference-title {
  font-size: 4.5rem;
  font-weight: 900;
  background: linear-gradient(90deg, #4a7fff, #00d4ff);
  -webkit-background-clip: text;
  color: transparent;
}

.conference-subtitle {
  font-size: 2.2rem;
  color: #ccd6ff;
  margin-bottom: 40px;
}

.hero-buttons {
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
}

.btn {
  padding: 20px 50px;
  font-size: 1.3rem;
  font-weight: 600;
  border-radius: 12px;
  position: relative;
  overflow: hidden;
  display: inline-flex;
  align-items: center;
  gap: 12px;
}

.btn::before {
  content: "";
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
  background: linear-gradient(90deg, #4a7fff, #0066ff);
  color: #fff;
}

.btn-email {
  background: transparent;
  border: 2px solid #4a7fff;
  color: #4a7fff;
}

.event-details {
  display: flex;
  justify-content: space-between;
  margin-top: 60px;
  padding: 40px;
  background: rgba(17, 17, 42, 0.7);
  border-radius: 20px;
  border: 1px solid #333355;
}

.date-time,
.location {
  font-size: 1.8rem;
  color: #ccd6ff;
}

.countdown-section {
  margin-top: 60px;
}

.timer {
  display: flex;
  justify-content: center;
  gap: 40px;
  flex-wrap: wrap;
}

.time-block {
  background: rgba(255, 255, 255, 0.05);
  padding: 25px 20px;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.time-value {
  font-size: 4.5rem;
  font-weight: 900;
  background: linear-gradient(90deg, #ff6b9d, #ff9966);
  -webkit-background-clip: text;
  color: transparent;
}

.time-label {
  font-size: 1.4rem;
  color: #8899cc;
  margin-top: 10px;
}

/* Анимации */
.fade-in {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.delay-1 { animation-delay: 0.2s; }
.delay-2 { animation-delay: 0.4s; }
.delay-3 { animation-delay: 0.6s; }
.delay-4 { animation-delay: 0.8s; }
.delay-5 { animation-delay: 1s; }

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
@media (max-width: 600px) {
  .conference-title {
    font-size: 2.8rem;
  }
  .timer {
    gap: 20px;
  }
}
</style>
