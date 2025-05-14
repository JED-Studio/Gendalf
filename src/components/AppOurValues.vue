<script>
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    const cards = [
      {
        title: 'Быть командой',
        text: 'Готовность вносить вклад в общие цели команды и достигать их.',
        img: 'value/Values4.png',
        imgNum: 'value/Vectornum.png',
      },
      {
        title: 'Побеждать и не сдаваться',
        text: 'Быть ориентированным на результат, настойчивым и не сдаваться перед трудностями.',
        img: 'value/Values3.png',
        imgNum: 'value/Vectornum.png',
      },
      {
        title: 'Заботиться о клиентах',
        text: 'Все сотрудники в нашей команде - веселые, добрые, умные и хорошо внимательные',
        img: 'value/Values1.png',
        imgNum: 'value/Vectornum.png',
      },
      {
        title: 'Быть увлеченным и ответственным',
        text: 'Вкладывать душу в то, что делаешь и получать от работы удовольствие.',
        img: 'value/Values2.png',
        imgNum: 'value/Vectornum.png',
      },
      {
        title: 'Быть увлеченным и ответственным',
        text: 'Вкладывать душу в то, что делаешь и получать от работы удовольствие.',
        img: 'value/Values2.png',
        imgNum: 'value/Vectornum.png',
      },
    ]
    return { cards }
  },
})
</script>

<template>
  <div class="app-ourValues__section">
    <div class="app-gendalf__container">
      <div class="app-ourValues">
        <h2>Наши ценности скажут о нас больше:</h2>
        <div class="app-ourValues__images">
          <div v-for="card in cards" :key="card" class="app-ourValues__image-item">
            <img :src="card.imgNum" alt="" class="app-ourValues__image-num" />
            <img :src="card.img" alt="" class="app-ourValues__image" />
            <div class="app-ourValues__text">
              <h3>{{ card.title }}</h3>
              <p>{{ card.text }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.app-ourValues__section {
  background-color: rgba(233, 233, 233, 1);
}

.app-ourValues__image-item {
  position: relative;
}

.app-ourValues__image-num {
  position: absolute;
  top: 0;
  left: 0;
}

.app-ourValues > h2 {
  color: rgba(0, 183, 236, 1);
  font-weight: 300;
  font-size: 36px;
  margin-bottom: 37px;
}

.app-ourValues__text > h3 {
  color: rgba(102, 102, 102, 1);
  font-weight: 700;
  font-size: 20px;
  margin-bottom: 8px;
  text-decoration: underline solid;
  line-height: 30px;
  text-align: center;
}

.app-ourValues__text > p {
  color: rgba(102, 102, 102, 1);
  font-weight: 400;
  font-size: 16px;
  line-height: 22px;
  text-align: center;
  margin-bottom: 90px;
}

.app-ourValues__images {
  width: 100%;
  display: flex;
  overflow-x: auto;
}

.app-ourValues__image {
  width: 284px;
}

.app-ourValues__images::-webkit-scrollbar {
  display: none;
}
</style>
