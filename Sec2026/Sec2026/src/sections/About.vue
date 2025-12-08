<template>
  <section class="what-await">
    <h3>Что вас ждёт:</h3>

    <div class="features-grid">
      <!-- Первая строка: иконка слева, текст справа -->
      <div class="feature-item left-icon">
        <div class="icon-container">
          <img
            src="https://s3.iimg.su/s/06/gDmGtUTxEuvHutattCXuoZLknAozh7I85pwFEw7f.png"
            alt="Портфель"
          />
        </div>
        <p>Выступления ведущих экспертов</p>
      </div>

      <!-- Вторая строка: текст слева, иконка справа -->
      <div class="feature-item right-icon">
        <p>Презентации инновационных проектов</p>
        <div class="icon-container">
          <img
            src="https://s3.iimg.su/s/06/g1xfPWPxOM2lN6J639r1DLjMSj6VvedeRWz14Fi4.png"
            alt="Презентация"
          />
        </div>
      </div>

      <!-- Третья строка: иконка слева, текст справа -->
      <div class="feature-item left-icon">
        <div class="icon-container">
          <img
            src="https://s3.iimg.su/s/06/g7ckoyuxmc4q8zFfjzZrPN916r1rbhuWvp4r6X5g.png"
            alt="Обмен"
          />
        </div>
        <p>Обмен опытом и знаниями</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ConferenceFeatures',
}
</script>

<style scoped>
.what-await {
  padding: 20px;
  background-color: black;
}

.features-grid {
  max-width: 660px;
  margin: 20px auto 0;
  display: flex;
  flex-direction: column;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 60px;
  margin-bottom: 15px;
  width: 100%;
  box-sizing: border-box;
  opacity: 0;
}

.feature-item.left-icon {
  justify-content: flex-start;
  transform: translateX(50px);
  animation: slideInFromRight 0.6s ease-out forwards;
}

.feature-item.right-icon {
  justify-content: flex-end;
  transform: translateX(-50px);
  animation: slideInFromLeft 0.6s ease-out forwards;
}

.icon-container {
  width: 129px;
  height: 120px;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  animation: fadeIn 0.6s ease-out 0.2s forwards;
}

.feature-item img {
  width: 129px;
  height: 120px;
}

h3 {
  color: #fff;
  margin-bottom: 20px;
  text-align: center;
  font-size: 26px;
}

p {
  margin: 0;
  font-size: 20px;
  min-width: 0;
  word-break: break-word;
  opacity: 0;
  animation: fadeIn 0.6s ease-out 0.1s forwards;
}

/* Анимации */
@keyframes slideInFromRight {
  from {
    transform: translateX(50px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes slideInFromLeft {
  from {
    transform: translateX(-50px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
