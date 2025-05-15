<script>
import { defineComponent } from 'vue'
import AppVector from './icons/AppVector.vue'
export default defineComponent({
  components: {
    AppVector,
  },
  setup() {},
})
</script>

<template>
  <div class="app-recruitingForm__section">
    <div class="app-gendalf__container">
      <div class="app-recruitingForm__containerFlex">
        <form class="app-recruitingForm">
          <h2>Записаться на собеседование</h2>
          <div class="app-recruitingForm__inputs">
            <input type="text" placeholder="Как к вам обращаться?" />
            <input type="text" placeholder="Телефон" />
            <input type="text" placeholder="Email" />
            <input type="text" placeholder="Желаемая должность" />
          </div>
          <h3>Выберите категорию занятости</h3>
          <div class="app-recruitingForm__checkboxes">
            <div class="app-recruitingForm__checkbox">
              <input type="radio" />
              <p>Работа в офисе</p>
            </div>
            <div class="app-recruitingForm__checkbox">
              <input type="radio" />
              <p>Стажировка</p>
            </div>
            <div class="app-recruitingForm__checkbox">
              <input type="radio" />
              <p>Удаленная работа</p>
            </div>
          </div>

          <textarea placeholder="Ваши вопросы"></textarea>

          <div class="app-recruitingForm__buttons">
            <div class="app-recruitingForm__resume">Прикрепить резюме</div>
            <div class="app-recruitingForm__sign-up">Записаться</div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-recruitingForm__inputs {
  margin-bottom: 17px;
}

.app-recruitingForm__resume {
  display: inline-block;
  border-radius: 5px;
  padding: 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  max-width: 270px;
  width: 100%;
  transition: all 0.3s ease;
  border: 1px solid rgba(155, 204, 55, 1);
}

.app-recruitingForm__sign-up {
  display: inline-block;
  border-radius: 5px;
  padding: 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  max-width: 218px;
  width: 100%;
  transition: all 0.3s ease;
  border: 1px solid rgba(155, 204, 55, 1);
}

.app-recruitingForm__resume:hover,
.app-recruitingForm__sign-up:hover {
  color: rgba(155, 204, 55, 1);
  background-color: white;
}

.app-recruitingForm__containerFlex {
  display: flex;
  justify-content: center;
}
.app-recruitingForm__section {
  position: relative;
  width: 100%;
  height: 840px;
  background-image: url('/value/Fon2.jpg');
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.app-recruitingForm__section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 47, 61, 0.77);
  z-index: 1;
}

.app-recruitingForm {
  align-items: center;
  max-width: 840px;
  width: 100%;
  position: relative;
  z-index: 2;
  text-align: center;
  color: #fff;
  background-color: rgba(0, 183, 236, 1);
  padding: 50px;
}
.app-recruitingForm > h3 {
  font-weight: 300;
  font-size: 36px;
  margin-bottom: 18px;
  margin-bottom: 10px;
}

.app-recruitingForm > h2 {
  font-weight: 300;
  font-size: 36px;
  margin-bottom: 18px;
}

.app-recruitingForm > textarea {
  display: block;
  width: 100%;
  max-width: 568px;
  margin: 0 auto;
  margin-bottom: 17px;
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  background-color: White;
  color: #fff;
  height: 108px;
}

.app-recruitingForm__inputs {
}

.app-recruitingForm__inputs > input {
  display: block;
  width: 100%;
  max-width: 568px;
  margin: 0 auto;
  margin-bottom: 10px;
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  background-color: White;
  color: #fff;
}

.app-recruitingForm__checkboxes {
  width: 100%;
  max-width: 568px;
  margin: 0 auto;
  margin-bottom: 17px;
}

.app-recruitingForm__checkbox {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
  gap: 6px;
}

.app-recruitingForm__checkbox > p {
  font-weight: 400;
  font-size: 18px;
}
.app-recruitingForm__checkbox > input {
  margin: 0;
}

.app-recruitingForm__buttons {
  width: 100%;
  max-width: 568px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
</style>
