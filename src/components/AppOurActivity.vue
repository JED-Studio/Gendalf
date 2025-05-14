<script>
import { defineComponent } from 'vue'
import AppPoligonOne from './icons/AppPoligonOne.vue'
import AppPoligonTwo from './icons/AppPoliogonTwo.vue'
import AppPoligonThree from './icons/AppPoligonThree.vue'

export default defineComponent({
  components: {
    AppPoligonOne,
    AppPoligonTwo,
    AppPoligonThree,
  },
  setup() {
    return {}
  },
})
</script>

<template>
  <div class="app-ourActivity__section">
    <div class="app-gendalf__container">
      <div class="app-ourActivity">
        <h2>О том, чем мы занимаемся</h2>
        <div class="app-ourActivity__containerFlex">
          <div class="app-ourActivity__info">
            <div class="app-ourActivity__info-text">
              <p>
                ГЭНДАЛЬФ – один из крупнейших игроков на рынке информационных технологий, занимающий
                4 место среди 7000 партнеров фирмы «1С». У нас есть представительства в 15 городах
                России, а нашими услугами пользуются 23 000 организаций-клиентов, в числе которых
                «Базэл Аэро», «Ростсельмаш», UTG. Аэропорт Кольцово и многие другие.
              </p>
              <p>
                Мы тщательно подходим к выбору сотрудников, которые становятся частью команды
                профессионалов.
              </p>
              <p>
                У нас работают специалисты разных областей: программисты, маркетологи, менеджеры,
                копирайтеры, методисты и другие, чей карьерный рост не ограничен привычными рамками.
              </p>
            </div>
            <div class="app-ourActivity__buttons">
              <div class="app-ourActivity__button-info">Узнать больше</div>
              <div class="app-ourActivity__button-interview">Записаться на собеседование</div>
            </div>
          </div>

          <div class="app-ourActivity__images">
            <img src="/public/Mask group.png" alt="" />

            <AppPoligonOne />
            <AppPoligonTwo />
            <AppPoligonThree />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.app-ourActivity__section {
  margin-bottom: 60px;
}

.app-ourActivity__containerFlex {
  display: flex;
  justify-content: space-between;
}

.app-ourActivity > h2 {
  font-weight: 300;
  font-size: 36px;
  color: rgba(0, 183, 236, 1);
  margin-bottom: 20px;
}

.app-ourActivity__info-text > p {
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  margin-bottom: 10px;
}

.app-ourActivity__info-text > p:last-child {
  margin-bottom: 0;
}

.app-ourActivity__info {
  width: 100%;
  max-width: 728px;
}

.app-ourActivity__info-text {
  margin-bottom: 20px;
}

.app-ourActivity__buttons {
}

.app-ourActivity__button-info {
  display: inline-block;
  border-radius: 5px;
  padding: 13px 16px;
  background-color: rgba(0, 183, 236, 1);
  color: #fff;
  width: 100%;
  max-width: 225px;
  text-align: center;
  margin-right: 20px;
  transition: all 0.3s ease;
  border: 1px solid rgba(0, 183, 236, 1);
}
.app-ourActivity__button-interview {
  display: inline-block;
  width: 100%;
  max-width: 320px;
  border-radius: 5px;
  padding: 13px 16px;
  background-color: rgba(0, 183, 236, 1);
  color: #fff;
  text-align: center;
  transition: all 0.3s ease;
  border: 1px solid rgba(0, 183, 236, 1);
}

.app-ourActivity__button-info:hover,
.app-ourActivity__button-interview:hover {
  cursor: pointer;
  background-color: #fff;
  color: rgba(0, 183, 236, 1);
}

.app-ourActivity__gran {
}

.app-ourActivity__images {
  position: relative;
}

@media (max-width: 768px) {
  .app-ourActivity > h2 {
    text-align: center;
  }
  .app-ourActivity__images {
    display: none;
  }

  .app-ourActivity__button-info,
  .app-ourActivity__button-interview {
    display: block;
    width: 100%;
    max-width: 295px;
    margin: 0 auto;
    margin-bottom: 10px;
  }
}
</style>
