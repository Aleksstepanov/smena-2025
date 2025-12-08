<template>
  <section class="hero">
    <BaseContainer>
      <div class="hero-grid">
        <!-- Левая часть -->
        <div class="hero-left">
          <h1 class="hero-title">SECON 2026</h1>
          <h2 class="hero-subtitle">IT конференция</h2>

          <div class="hero-buttons">
            <button class="btn btn-gray">Купить билет</button>
            <button class="btn btn-blue">Отправить email</button>
          </div>

          <div class="event-info">
            <p class="event-date">1–2 февраля в&nbsp;12:00</p>
            <p class="event-location">
              Пенза, ул. Попова 66 к.1 Центр “Ключевский”
            </p>
          </div>

          <div class="countdown">
            <div class="cd-item">
              <div class="cd-value">{{ days }}</div>
              <div class="cd-label">Дни</div>
            </div>
            <div class="cd-divider"></div>

            <div class="cd-item">
              <div class="cd-value">{{ hours }}</div>
              <div class="cd-label">Часы</div>
            </div>
            <div class="cd-divider"></div>

            <div class="cd-item">
              <div class="cd-value">{{ minutes }}</div>
              <div class="cd-label">Минуты</div>
            </div>
            <div class="cd-divider"></div>

            <div class="cd-item">
              <div class="cd-value">{{ seconds }}</div>
              <div class="cd-label">Секунды</div>
            </div>
          </div>
        </div>

        <!-- Правая часть иллюстрации -->
        <div class="hero-right">
          <img src="@/assets/hero-graphic.png" class="hero-image" alt="" />
        </div>
      </div>
    </BaseContainer>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import BaseContainer from "@/components/BaseContainer.vue";

// Таймер
const days = ref("00");
const hours = ref("00");
const minutes = ref("00");
const seconds = ref("00");

const target = new Date("2026-02-01T12:00:00").getTime();

function update() {
  const now = Date.now();
  const diff = target - now;

  if (diff < 0) return;

  days.value = Math.floor(diff / 86400000).toString();
  hours.value = Math.floor((diff / 3600000) % 24).toString();
  minutes.value = Math.floor((diff / 60000) % 60).toString();
  seconds.value = Math.floor((diff / 1000) % 60).toString();
}

onMounted(() => {
  update();
  setInterval(update, 1000);
});
</script>

<style scoped>
/* Общий фон секции */
.hero {
  padding-top: 120px;
  padding-bottom: 80px;
  background: #000;
  position: relative;
  overflow: hidden;
}

/* Основная сетка */
.hero-grid {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
}

/* Левая часть */
.hero-left {
  width: 60%;
}

/* Заголовки */
.hero-title {
  font-size: 64px;
  font-weight: 800;
  color: #ffffff;
  margin-bottom: 10px;
}

.hero-subtitle {
  font-size: 58px;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 30px;
}

/* Кнопки */
.hero-buttons {
  display: flex;
  gap: 20px;
  margin-bottom: 40px;
}

.btn {
  padding: 12px 34px;
  font-size: 18px;
  border-radius: 14px;
  font-weight: 500;
  border: none;
  cursor: pointer;
}

.btn-gray {
  background: #848484;
  color: white;
}

.btn-blue {
  background: #1b2f57;
  color: white;
}

/* Дата и место */
.event-info {
  margin-bottom: 40px;
}

.event-date {
  color: white;
  font-size: 18px;
  margin-bottom: 6px;
}

.event-location {
  color: #568dfc;
  font-size: 18px;
}

/* Таймер */
.countdown {
  display: flex;
  align-items: center;
  gap: 35px;
  margin-top: 20px;
}

.cd-item {
  text-align: center;
}

.cd-value {
  color: white;
  font-size: 36px;
  font-weight: 700;
}

.cd-label {
  color: white;
  font-size: 18px;
}

.cd-divider {
  width: 1px;
  height: 46px;
  background: white;
  opacity: 0.6;
}

/* Правая часть */
.hero-right {
  width: 40%;
  display: flex;
  justify-content: center;
}

.hero-image {
  width: 100%;
  max-width: 520px;
  opacity: 0.9;
}
</style>
