<script>
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    const items = [
      {
        img: 'adobestock/AdobeStock1.png',
        title: 'Экономим на бумаге и угадываем фильмы: дайджест видео марта 2022 года',
      },
      {
        img: 'adobestock/AdobeStock3.png',
        title: 'Изменения 2022 года',
      },
      {
        img: 'adobestock/AdobeStock4.png',
        title: 'Почему стоит работать программистом в 2022 году',
      },
      {
        img: 'adobestock/AdobeStock5.png',
        title:
          'Автоматизированный УСН и путевые листы: дайджест новостей за март 2022. Автоматизированный УСН и путевые листы',
      },
      {
        img: 'adobestock/AdobeStock4.png',
        title: 'Почему стоит работать программистом в 2022 году',
      },
      {
        img: 'adobestock/AdobeStock5.png',
        title:
          'Автоматизированный УСН и путевые листы: дайджест новостей за март 2022. Автоматизированный УСН и путевые листы',
      },
      {
        img: 'adobestock/AdobeStock4.png',
        title: 'Почему стоит работать программистом в 2022 году',
      },
      {
        img: 'adobestock/AdobeStock5.png',
        title:
          'Автоматизированный УСН и путевые листы: дайджест новостей за март 2022. Автоматизированный УСН и путевые листы',
      },
    ]

    return {
      items,
    }
  },
})
</script>

<template>
  <div class="app-nowStream__section">
    <div class="app-gendalf__container">
      <div class="app-nowStream">
        <h2>Живая лента</h2>
        <div class="app-nowStream__cards">
          <div v-for="item in items" :key="item" class="app-nowStream__card">
            <img :src="item.img" alt="" />
            <div class="app-nowStream__card-text">
              <p>{{ item.title }}</p>
              <div class="app-nowStream__card-button">Перейти к статье</div>
            </div>
          </div>
        </div>
        <div class="app-nowStream__arrows">
          <img class="app-nowStream__arrows-left" src="/public/стрелка лева.png" alt="" />
          <img class="app-nowStream__arrows-right" src="/public/стрелка право.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-nowStream__cards::-webkit-scrollbar {
  display: none;
}

.app-nowStream {
  position: relative;
  margin-bottom: 47px;
}
.app-nowStream > h2 {
  font-family: 300;
  font-size: 36px;
  color: rgba(0, 183, 236, 1);
  margin-bottom: 21px;
}

.app-nowStream__arrows-left {
  position: absolute;
  top: 50%;
  left: 0;
  cursor: pointer;
}

.app-nowStream__arrows-right {
  position: absolute;
  top: 50%;
  right: 0;
  cursor: pointer;
}

.app-nowStream__cards {
  width: 100%;
  gap: 30px;
  display: flex;
  overflow-x: auto;
  padding: 5px 0;
}

.app-nowStream__card {
  display: flex;
  flex-direction: column;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 1), rgba(7, 168, 219, 0.1));
  overflow: hidden;
  width: 100%;
  max-width: 272px;
  border-radius: 5px;
  box-shadow: 0px 0px 5px 0px rgba(102, 102, 102, 0.7);
  border: 2px solid #fff;
  min-width: calc(1088px / 4);
}

.app-nowStream__card img {
  width: 100%;
}

.app-nowStream__card-text {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 25px 25px 25px 25px;
}

.app-nowStream__card-text > P {
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  margin-bottom: 20px;
}

.app-nowStream__card-button {
  color: rgba(0, 183, 236, 1);
  border-radius: 5px;
  border: 1px solid rgba(0, 183, 236, 1);
  padding: 10px 20px;
  text-align: center;
  margin-top: auto;
}
</style>
