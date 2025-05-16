<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  components: {},
  setup() {
    const name = ref('')
    const phone = ref('')
    const email = ref('')
    const position = ref('')

    const isValid = ref({
      name: true,
      phone: true,
      email: true,
      position: true,
    })

    const validateInputs = () => {
      isValid.value.name = name.value.trim() !== ''
      isValid.value.phone = phone.value.trim() !== ''
      isValid.value.email = email.value.trim() !== ''
      isValid.value.position = position.value.trim() !== ''
      return (
        isValid.value.name && isValid.value.phone && isValid.value.email && isValid.value.position
      )
    }

    const onSubmit = () => {
      const allValid = validateInputs()
      if (allValid) {
        alert('Форма успешно отправлена!')
      } else {
        alert('Пожалуйста, заполните все поля корректно.')
      }
    }

    return {
      name,
      phone,
      email,
      position,
      isValid,
      onSubmit,
    }
  },
})
</script>

<template>
  <div class="app-recruitingForm__section">
    <div class="app-gendalf__container">
      <div class="app-recruitingForm__containerFlex">
        <form class="app-recruitingForm" @submit.prevent>
          <h2>Записаться на собеседование</h2>
          <div class="app-recruitingForm__inputs">
            <div class="app-recruitingForm__input-container">
              <input
                type="text"
                placeholder="Как к вам обращаться?"
                v-model="name"
                :class="{ invalid: !isValid.name, valid: isValid.name && name }"
              />
              <img
                v-if="!isValid.name"
                src="/public/Group 179.png"
                alt="Invalid"
                class="status-icon"
              />
              <img
                v-else-if="isValid.name && name"
                src="/public/Group 180.png"
                alt="Valid"
                class="status-icon"
              />
            </div>
            <div class="app-recruitingForm__input-container">
              <input
                type="text"
                placeholder="Телефон"
                v-model="phone"
                :class="{ invalid: !isValid.phone, valid: isValid.phone && phone }"
              />
              <img
                v-if="!isValid.phone"
                src="/public/Group 179.png"
                alt="Invalid"
                class="status-icon"
              />
              <img
                v-else-if="isValid.phone && phone"
                src="/public/Group 180.png"
                alt="Valid"
                class="status-icon"
              />
            </div>
            <div class="app-recruitingForm__input-container">
              <input
                type="text"
                placeholder="Email"
                v-model="email"
                :class="{ invalid: !isValid.email, valid: isValid.email && email }"
              />
              <img
                v-if="!isValid.email"
                src="/public/Group 179.png"
                alt="Invalid"
                class="status-icon"
              />
              <img
                v-else-if="isValid.email && email"
                src="/public/Group 180.png"
                alt="Valid"
                class="status-icon"
              />
            </div>
            <div class="app-recruitingForm__input-container">
              <input
                type="text"
                placeholder="Желаемая должность"
                v-model="position"
                :class="{ invalid: !isValid.position, valid: isValid.position && position }"
              />
              <img
                v-if="!isValid.position"
                src="/public/Group 179.png"
                alt="Invalid"
                class="status-icon"
              />
              <img
                v-else-if="isValid.position && position"
                src="/public/Group 180.png"
                alt="Valid"
                class="status-icon"
              />
            </div>
          </div>
          <h3>Выберите категорию занятости</h3>
          <div class="app-recruitingForm__checkboxes">
            <div class="app-recruitingForm__checkbox">
              <input type="radio" name="employment" />
              <p>Работа в офисе</p>
            </div>
            <div class="app-recruitingForm__checkbox">
              <input type="radio" name="employment" />
              <p>Стажировка</p>
            </div>
            <div class="app-recruitingForm__checkbox">
              <input type="radio" name="employment" />
              <p>Удаленная работа</p>
            </div>
          </div>

          <textarea placeholder="Ваши вопросы"></textarea>

          <div class="app-recruitingForm__buttons">
            <div class="app-recruitingForm__resume">Прикрепить резюме</div>
            <div class="app-recruitingForm__sign-up" @click="onSubmit">Записаться</div>
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
.app-recruitingForm__input-container {
  position: relative;
  max-width: 568px;
  margin: 0 auto 10px auto;
}
.app-recruitingForm__input-container > input {
  display: block;
  width: 100%;
  padding: 10px 40px 10px 20px;
  border-radius: 5px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  font-size: 16px;
  color: #000;
  background-color: white;
  box-sizing: border-box;
}

input.invalid {
  border-color: #e74c3c;
}

input.valid {
  border-color: #2ecc71;
}

.status-icon {
  position: absolute;
  right: 10px;
  top: 50%;
  width: 20px;
  height: 20px;
  transform: translateY(-50%);
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
  text-align: center;
  user-select: none;
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
  margin: 0 auto 17px auto;
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  background-color: white;
  color: #000;
  height: 108px;
  box-sizing: border-box;
}
.app-recruitingForm__checkboxes {
  width: 100%;
  max-width: 568px;
  margin: 0 auto 17px auto;
  text-align: left;
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
  color: #fff;
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
