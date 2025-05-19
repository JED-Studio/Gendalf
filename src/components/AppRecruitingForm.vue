<script>
import { defineComponent, ref } from 'vue'
import AppVector from './icons/AppVector.vue'

export default defineComponent({
  components: {
    AppVector,
  },
  setup() {
    const svgColor = ref('#fff')
    const name = ref('')
    const phone = ref('')
    const email = ref('')
    const position = ref('')
    const employmentCategory = ref(null)
    const resumeFile = ref(null)

    const isValid = ref({
      name: true,
      phone: true,
      email: true,
      position: true,
      employmentCategory: true,
      resumeAttached: true,
    })

    const validateInputs = () => {
      isValid.value.name = name.value.trim() !== ''
      isValid.value.phone = phone.value.trim() !== ''
      isValid.value.email = email.value.trim() !== ''
      isValid.value.position = position.value.trim() !== ''
      isValid.value.employmentCategory = employmentCategory.value !== null
      isValid.value.resumeAttached = resumeFile.value !== null

      return (
        isValid.value.name &&
        isValid.value.phone &&
        isValid.value.email &&
        isValid.value.position &&
        isValid.value.employmentCategory &&
        isValid.value.resumeAttached
      )
    }

    const onSubmit = () => {
      const allValid = validateInputs()
      if (allValid) {
        alert('Форма успешно отправлена!')
      } else {
        alert('Пожалуйста, заполните все поля корректно и прикрепите резюме.')
      }
    }

    const onFileChange = (event) => {
      const files = event.target.files
      if (files && files.length > 0) {
        resumeFile.value = files[0]
      } else {
        resumeFile.value = null
      }
    }

    return {
      name,
      phone,
      email,
      position,
      employmentCategory,
      resumeFile,
      isValid,
      onSubmit,
      onFileChange,
      svgColor,
    }
  },
})
</script>

<template>
  <div class="app-recruitingForm__section">
    <div class="app-gendalf__container">
      <div class="app-recruitingForm__containerFlex">
        <form class="app-recruitingForm" @submit.prevent>
          <div class="app-recruitingForm__form">
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

            <div class="app-recruitingForm__radio-group">
              <label class="app-recruitingForm__radio-option">
                <input
                  id="employment-office"
                  type="radio"
                  name="employment"
                  value="office"
                  @change="employmentCategory = 'office'"
                />
                <span class="radio-custom"></span>
                Работа в офисе
              </label>

              <label class="app-recruitingForm__radio-option">
                <input
                  id="employment-internship"
                  type="radio"
                  name="employment"
                  value="internship"
                  @change="employmentCategory = 'internship'"
                />
                <span class="radio-custom"></span>
                Стажировка
              </label>

              <label class="app-recruitingForm__radio-option">
                <input
                  id="employment-remote"
                  type="radio"
                  name="employment"
                  value="remote"
                  @change="employmentCategory = 'remote'"
                />
                <span class="radio-custom"></span>
                Удаленная работа
              </label>
            </div>

            <textarea placeholder="Ваши вопросы"></textarea>

            <div class="app-recruitingForm__buttons">
              <label
                for="resume-upload"
                class="app-recruitingForm__resume"
                :class="{ invalid: !isValid.resumeAttached }"
                tabindex="0"
                @mouseover="svgColor = '#9BCC37'"
                @mouseleave="svgColor = '#fff'"
              >
                {{ resumeFile ? resumeFile.name : 'Прикрепить резюме' }}
                <AppVector :color="svgColor" />
              </label>
              <input
                id="resume-upload"
                type="file"
                accept=".pdf,.doc,.docx"
                style="display: none"
                @change="onFileChange"
              />
              <div class="app-recruitingForm__sign-up" @click="onSubmit">Записаться</div>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-recruitingForm__form {
  max-width: 568px;
  margin: 0 auto;
}

.app-recruitingForm__inputs {
  margin-bottom: 17px;
}
.app-recruitingForm__input-container {
  position: relative;

  margin-bottom: 10px;
}
.app-recruitingForm__input-container > input {
  display: block;
  width: 100%;
  padding: 15px 40px 15px 16px;
  border-radius: 5px;
  border: 1px solid rgba(102, 102, 102, 0.9);
  font-size: 16px;
  color: #000;
  background-color: white;
  box-sizing: border-box;
}

.app-recruitingForm__input-container > input::placeholder {
  font-weight: 300;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  opacity: 50%;
}

input.invalid {
  border-color: rgba(253, 117, 131, 1);
}

input.valid {
  border-color: #2ecc71;
}

.status-icon {
  position: absolute;
  right: 23px;
  top: 50%;
  width: 31px;
  height: 31px;
  transform: translateY(-50%);
}
.app-recruitingForm__resume {
  position: relative;
  display: inline-block;
  border-radius: 5px;
  padding: 13px 20px 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  max-width: 270px;
  width: 100%;
  transition: all 0.3s ease;
  border: 2px solid rgba(155, 204, 55, 1);
  user-select: none;
  text-align: center;
}
.app-recruitingForm__resume.invalid {
  border-color: #e74c3c;
  background-color: #f8d7da;
  color: #721c24;
}
.app-recruitingForm__resume:hover {
  color: rgba(155, 204, 55, 1);
  background-color: white;
  border-color: rgba(155, 204, 55, 1);
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
  border: 2px solid rgba(155, 204, 55, 1);
  text-align: center;
  user-select: none;
}
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
  opacity: 90%;
}

.app-recruitingForm__form > h3 {
  font-weight: 700;
  font-size: 18px;
  margin-bottom: 10px;
  text-align: left;
}

.app-recruitingForm__form > h2 {
  font-weight: 300;
  font-size: 36px;
  margin-bottom: 18px;
}

.app-recruitingForm__form > textarea {
  width: 100%;
  margin-bottom: 17px;
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid rgba(102, 102, 102, 0.9);
  background-color: white;
  color: #000;
  height: 108px;
  resize: none;
}

.app-recruitingForm__form > textarea::placeholder {
  font-weight: 300;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  opacity: 50%;
}

.app-recruitingForm__radio-group {
  margin-bottom: 17px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.app-recruitingForm__radio-option {
  display: flex;
  align-items: center;
  gap: 6px;
  font-weight: 400;
  font-size: 18px;
  color: #fff;
  cursor: pointer;
}

.app-recruitingForm__radio-option input[type='radio'] {
  display: none;
}

.app-recruitingForm__radio-option input[type='radio']:checked + .radio-custom {
  border-color: white;
}
.app-recruitingForm__radio-option input[type='radio']:checked + .radio-custom::after {
  display: block;
}

.radio-custom {
  width: 16px;
  height: 16px;
  border: 1px solid white;
  border-radius: 50%;
  position: relative;
}

.radio-custom::after {
  content: '';
  width: 10px;
  height: 10px;
  background: #ffffff;
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: none;
}

.app-recruitingForm__buttons {
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

@media (max-width: 768px) {
  .app-recruitingForm__buttons {
    display: block;
  }

  .app-recruitingForm__resume {
    max-width: 100%;
    margin-bottom: 6px;
  }

  .app-recruitingForm__sign-up {
    max-width: 100%;
  }

  .app-recruitingForm__form > textarea {
    height: 50px;
  }
}
</style>
