<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="links-section">
        <div class="links">
          <a href="/user-agreement" class="link">Пользовательское соглашение</a>
          <a href="/privacy-policy" class="link">Политика в отношении обработки персональных данных</a>
        </div>
        
        <div class="social">
          <a href="https://t.me/example" target="_blank" class="social-link">
            <img :src="telegramIcon" alt="Telegram" class="icon">
          </a>
          <a href="https://vk.com/example" target="_blank" class="social-link">
            <img :src="vkIcon" alt="VK" class="icon">
          </a>
        </div>
      </div>
      
      <div class="logo-section">
        <img :src="seconLogo" alt="SECON" class="logo-img">
      </div>
    </div>
  </footer>
</template>

<script setup>
import telegramIcon from '@/assets/icons/telegram-icon.svg'
import vkIcon from '@/assets/icons/vk-icon.svg'
import seconLogo from '@/assets/icons/secon-logo.svg'
</script>

<style scoped>
.footer {
  background-color: #192644;
  color: white;
  font-family: Arial, sans-serif;
  padding: 20px 0;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.links-section {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.link {
  text-decoration: none;
  color: white;
  font-size: 14px;
  transition: color 0.3s ease;
  line-height: 1.4;
}

.link:hover {
  color: #4a9eff;
  text-decoration: underline;
}

.social {
  display: flex;
  gap: 15px;
}

.social-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.social-link:hover {
  background-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.icon {
  width: 20px;
  height: 20px;
  filter: brightness(0) invert(1);
}

.logo-img {
  width: 110px;
  height: 110px;
}

/* Планшет (768px - 1199px) */
@media (max-width: 1199px) {
  .footer-content {
    max-width: 768px;
    padding: 0 30px;
  }
  
  .logo-img {
    width: 90px;
    height: 90px;
  }
}

/* Планшет вертикально / Мобильный горизонтально (480px - 767px) */
@media (max-width: 767px) {
  .footer-content {
    flex-direction: column;
    gap: 30px;
    text-align: center;
  }
  
  .links-section {
    align-items: center;
  }
  
  .links {
    align-items: center;
  }
  
  .logo-img {
    width: 80px;
    height: 80px;
  }
}

/* Мобильный вертикально (до 479px) */
@media (max-width: 479px) {
  .footer {
    padding: 15px 0;
  }
  
  .footer-content {
    padding: 0 15px;
    gap: 25px;
  }
  
  .link {
    font-size: 13px;
  }
  
  .social-link {
    width: 32px;
    height: 32px;
  }
  
  .icon {
    width: 18px;
    height: 18px;
  }
  
  .logo-img {
    width: 70px;
    height: 70px;
  }
}

/* Очень маленькие экраны (до 320px) */
@media (max-width: 320px) {
  .links {
    gap: 8px;
  }
  
  .link {
    font-size: 12px;
  }
  
  .social {
    gap: 10px;
  }
  
  .social-link {
    width: 30px;
    height: 30px;
  }
  
  .icon {
    width: 16px;
    height: 16px;
  }
  
  .logo-img {
    width: 60px;
    height: 60px;
  }
}
</style>