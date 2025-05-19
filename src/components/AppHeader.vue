<template>
  <header>
    <div class="app-gendalf__container">
      <div class="app-header">
        <img class="app-header-logo desktop-logo" src="/public/Group 156.png" alt="Логотип" />

        <nav class="app-header-nav desktop-nav">
          <a href="#">Профориентация</a>
          <a href="#">Выбрать вакансию</a>
          <a href="#">Карьера в ГЭНДАЛЬФ</a>
          <a href="#">Стажерство</a>
          <a href="#">Отзывы</a>
        </nav>

        <div class="app-header__button desktop-button">Запись на собеседование</div>

        <div class="mobile-header">
          <img src="/public/header/Vector (1).png" alt="Иконка 1" class="mobile-icon" />
          <img src="/public/header/Group.png" alt="Иконка 2" class="mobile-icon" />

          <img class="mobile-logo" src="/public/header/logo.png" alt="Логотип" />

          <img src="/public/header/иконка моя страница.png" alt="Иконка 3" class="mobile-icon" />
          <img
            src="/public/header/Иконка Бургер.png"
            alt="Меню"
            class="burger-icon"
            @click="toggleSidebar"
          />
        </div>
      </div>
    </div>

    <div class="sidebar" :class="{ active: isSidebarOpen }">
      <img @click="closreSidebar" width="30px" src="/public/header/крестик.png" alt="" />
      <nav class="mobile-nav">
        <a href="#">Профориентация</a>
        <a href="#">Выбрать вакансию</a>
        <a href="#">Карьера в ГЭНДАЛЬФ</a>
        <a href="#">Стажерство</a>
        <a href="#">Отзывы</a>
      </nav>
      <div class="app-header__button mobile-button">Запись на собеседование</div>
    </div>
  </header>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const isSidebarOpen = ref(false)

    const toggleSidebar = () => {
      isSidebarOpen.value = !isSidebarOpen.value
    }

    const closreSidebar = () => {
      isSidebarOpen.value = false
    }

    return {
      isSidebarOpen,
      toggleSidebar,
      closreSidebar,
    }
  },
}
</script>

<style>
header {
  background-color: rgba(0, 183, 236, 1);
  position: relative;
}

.app-header {
  padding: 10px 30px;
  position: relative;
}

.app-header-logo,
.app-header-nav,
.app-header__button {
  display: inline-block;
  vertical-align: middle;
}

.app-header > img {
  width: 74px;
  margin-right: 31px;
}

.app-header-nav > a {
  margin-right: 39px;
  color: rgba(255, 255, 255, 1);
  text-decoration: none;
  font-weight: 400;
  font-size: 18px;
  line-height: 100%;
  letter-spacing: 0%;
}

nav > a:last-child {
  margin-right: 61px;
}

.app-header__button {
  background-color: rgba(255, 255, 255, 1);
  color: rgba(0, 183, 236, 1);
  padding: 7px 14px;
  border-radius: 5px;
  cursor: pointer;
}

/* Мобильная версия (изначально скрыта) */
.mobile-header {
  display: none;
}

.mobile-icon,
.burger-icon {
  cursor: pointer;
}

/* Сайдбар */
.sidebar {
  position: fixed;
  top: 0;
  right: -100%;
  width: 70%;
  height: 100vh;
  background-color: rgba(0, 183, 236, 1);
  transition: right 0.3s ease;
  z-index: 1000;
  padding: 20px;
  box-sizing: border-box;
}

.sidebar.active {
  right: 0;
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  margin-top: 50px;
}

.mobile-nav a {
  color: white;
  text-decoration: none;
  margin-bottom: 20px;
  font-size: 18px;
}

.mobile-button {
  margin-top: 20px;
}

/* Медиа-запрос для мобильной версии */
@media (max-width: 1200px) {
  header {
    background-color: rgb(255, 255, 255);
  }

  .desktop-nav,
  .desktop-button,
  .desktop-logo {
    display: none !important;
  }

  .mobile-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }

  .mobile-logo {
    width: 74px;
  }
}
</style>
