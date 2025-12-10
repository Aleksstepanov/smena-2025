<template>
  <div class="speakers-page">
    <h3 class="speakers-title">Спикеры</h3>
    <div class="container">
      <div v-for="speaker in speakers" :key="speaker.id" class="card">
        <img :src="speaker.image" :alt="speaker.name" class="card-img" />
        <div class="card-content">
          <div class="name">{{ speaker.name }}</div>
          <div class="position">{{ speaker.position }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const speakers = ref([
  {
    id: 1,
    name: 'Павел Павлович Павленко',
    position: 'Технический директор',
    image: 'https://s.iimg.su/s/10/gN4AsOyxEgEfeqNeVUbzzmUTkGVgdRrnIQu7VqRO.jpg',
  },
  {
    id: 2,
    name: 'Анна Сергеевна Иванова',
    position: 'Финансовый директор',
    image: 'https://s.iimg.su/s/10/gzzhZgDxzR7thhPBzUL3JepGXn7aZ1oA94WSlTbI.jpg',
  },
  {
    id: 3,
    name: 'Дмитрий Алексеевич Смирнов',
    position: 'Руководитель отдела разработки',
    image: 'https://s.iimg.su/s/10/gHCW4i4xOQJu1DH8N8sDqzRPunZHrp3ekEabEBEh.jpg',
  },
])
</script>

<style>
:root {
  --bg-color: #000000;
  --card-bg: #3b4765;
  --text-white: #ffffff;
  --padding-outer: 100px;
  --gap-mobile: 20px;
}

.speakers-page {
  background-color: var(--bg-color);
  font-family: 'Space Grotesk', sans-serif;
}

.speakers-page {
  padding-top: 80px;
}

.speakers-title {
  color: var(--text-white);
  margin: 0 0 20px 0;
  padding-left: var(--padding-outer);
  font-size: 36px;
  line-height: 1.2;
}

.container {
  display: flex;
  justify-content: space-between;
  padding: 0 var(--padding-outer);
  flex-wrap: wrap; /* Для переноса на мобильных */
  gap: var(--gap-mobile);
}

.card {
  width: 350px;
  height: 500px;
  background-color: var(--card-bg);
  border-radius: 32px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.card-img {
  width: 100%;
  height: 350px;
  border-radius: 32px 32px 0 0;
  object-fit: cover;
}

.card-content {
  padding: 16px;
  flex: 1;
}

.name {
  font-size: 24px;
  color: var(--text-white);
  margin-bottom: 4px;
  text-align: left;
  font-weight: bold;
}

.position {
  font-size: 16px;
  color: var(--text-white);
  text-align: left;
  font-weight: normal;
}

/* Адаптивность: планшеты и мобильные */
@media (max-width: 1200px) {
  .container {
    justify-content: center;
    padding: 0 50px;
  }
}

@media (max-width: 768px) {
  .speakers-title {
    padding-left: 50px;
    font-size: 30px;
  }

  .container {
    padding: 0 20px;
    flex-direction: column;
    align-items: center;
  }

  .card {
    width: 100%;
    max-width: 350px;
  }
}

@media (max-width: 480px) {
  .speakers-title {
    padding-left: 20px;
    font-size: 26px;
  }

  .container {
    padding: 0 10px;
  }
}
</style>
