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
              Пенза, ул. Попова 66 к.1 Центр "Ключевский"
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

  days.value = Math.floor(diff / 86400000).toString().padStart(2, "0");
  hours.value = Math.floor((diff / 3600000) % 24).toString().padStart(2, "0");
  minutes.value = Math.floor((diff / 60000) % 60).toString().padStart(2, "0");
  seconds.value = Math.floor((diff / 1000) % 60).toString().padStart(2, "0");
}

onMounted(() => {
  update();
  setInterval(update, 1000);
});
</script>

<style scoped>
/* Общий фон секции */
.hero {
  padding-top: 80px;
  padding-bottom: 60px;
  background: #000;
  position: relative;
  overflow: hidden;
}

/* Основная сетка */
.hero-grid {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

/* Левая часть */
.hero-left {
  width: 100%;
  order: 2;
}

/* Правая часть */
.hero-right {
  width: 100%;
  order: 1;
  display: flex;
  justify-content: center;
}

.hero-image {
  width: 100%;
  max-width: 350px;
  opacity: 0.9;
}

/* Заголовки */
.hero-title {
  font-size: 42px;
  font-weight: 800;
  color: #ffffff;
  margin-bottom: 8px;
  text-align: center;
}

.hero-subtitle {
  font-size: 32px;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 30px;
  text-align: center;
}

/* Кнопки */
.hero-buttons {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-bottom: 30px;
}

.btn {
  padding: 16px 20px;
  font-size: 16px;
  border-radius: 12px;
  font-weight: 500;
  border: none;
  cursor: pointer;
  width: 100%;
  text-align: center;
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
  text-align: center;
}

.event-date {
  color: white;
  font-size: 18px;
  margin-bottom: 8px;
}

.event-location {
  color: #568dfc;
  font-size: 16px;
  line-height: 1.4;
}

/* Таймер */
.countdown {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  margin-top: 20px;
  flex-wrap: wrap;
}

.cd-item {
  text-align: center;
  min-width: 60px;
}

.cd-value {
  color: white;
  font-size: 32px;
  font-weight: 700;
  line-height: 1;
}

.cd-label {
  color: white;
  font-size: 14px;
  margin-top: 4px;
}

.cd-divider {
  width: 1px;
  height: 36px;
  background: white;
  opacity: 0.6;
  display: none;
}

/* Десктопная версия */
@media (min-width: 768px) {
  .hero {
    padding-top: 120px;
    padding-bottom: 80px;
  }
  
  .hero-grid {
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    gap: 40px;
  }
  
  .hero-left {
    width: 60%;
    order: 1;
  }
  
  .hero-right {
    width: 40%;
    order: 2;
  }
  
  .hero-image {
    max-width: 520px;
  }
  
  .hero-title {
    font-size: 64px;
    text-align: left;
  }
  
  .hero-subtitle {
    font-size: 58px;
    text-align: left;
  }
  
  .hero-buttons {
    flex-direction: row;
    gap: 20px;
  }
  
  .btn {
    width: auto;
    padding: 12px 34px;
    font-size: 18px;
  }
  
  .event-info {
    text-align: left;
  }
  
  .event-date {
    font-size: 18px;
  }
  
  .event-location {
    font-size: 18px;
  }
  
  .countdown {
    justify-content: flex-start;
    gap: 35px;
    flex-wrap: nowrap;
  }
  
  .cd-item {
    min-width: auto;
  }
  
  .cd-value {
    font-size: 36px;
  }
  
  .cd-label {
    font-size: 18px;
  }
  
  .cd-divider {
    display: block;
  }
}

/* Планшеты */
@media (min-width: 480px) and (max-width: 767px) {
  .hero-buttons {
    flex-direction: row;
    flex-wrap: wrap;
  }
  
  .btn {
    flex: 1;
    min-width: 200px;
  }
  
  .countdown {
    gap: 25px;
  }
  
  .cd-divider {
    display: block;
  }
}

/* Очень маленькие экраны */
@media (max-width: 359px) {
  .hero-title {
    font-size: 36px;
  }
  
  .hero-subtitle {
    font-size: 28px;
  }
  
  .cd-value {
    font-size: 28px;
  }
  
  .cd-label {
    font-size: 12px;
  }
  
  .countdown {
    gap: 15px;
  }
}
</style>