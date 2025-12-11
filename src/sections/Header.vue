<template>
  <div class="headersed">
    <div class="burger-menu" @click="toggleMenu">
      <div class="burger-line"></div>
      <div class="burger-line"></div>
      <div class="burger-line"></div>
    </div>
    <img
      src="https://s4.iimage.su/s/08/g24T81OxwzzyfHf2ZbHveFlBMAL0EX2DVOeng7uz.png"
      alt="Логотип"
      class="logo"
      width="255"
      height="60"
    />
    <button class="login-button" @click="handleLogin">Войти</button>
  </div>
</template>

<script>
export default {
  name: 'HeaderSED',
  methods: {
    toggleMenu() {
      // Логика открытия/закрытия меню (реализуется по необходимости)
      console.log('Меню открыто')
    },
    handleLogin() {
      // Логика обработки входа (например, переход на страницу авторизации)
      console.log('Переход на страницу входа')
    },
  },
}
</script>

<style scoped>
body {
  background-color: black;
  margin: 0;
  padding: 0;
}

.headersed {
  height: 100px;
  background-color: rgba(50, 76, 136, 0.5); /* #324C88 с 50% прозрачностью */
  position: relative;
  margin: 0 auto;
  width: 100%;
  box-sizing: border-box;
  display: flex;
  align-items: center;
}

.burger-menu {
  position: absolute;
  left: 17px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}

.burger-line {
  width: 30px;
  height: 3px;
  background-color: white;
  margin: 10px 0;
  display: block;
}

.login-button {
  position: absolute;
  right: 13px;
  top: 50%;
  transform: translateY(-50%);
  width: 79px;
  height: 39px;
  padding: 0;
  font-family: 'Monda', sans-serif;
  font-size: 23px;
  font-weight: 700;
  line-height: 39px;
  text-align: center;
  color: white;
  background: transparent;
  border: none;
  cursor: pointer;
}

.logo {
  margin: auto;
  display: block;
}
</style>
