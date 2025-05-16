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
      <div class="app-nowStream__container">
        <div class="app-nowStream">
          <h2>Живая лента</h2>
          <swiper-container
            class="app-nowStream__cards"
            :slides-per-view="'auto'"
            :space-between="30"
            :navigation="{
              nextEl: '.app-nowStream__arrows-right',
              prevEl: '.app-nowStream__arrows-left',
            }"
            :centered-slides="false"
            :loop="false"
          >
            <swiper-slide v-for="item in items" :key="item" class="app-nowStream__card">
              <img :src="item.img" alt="" />
              <div class="app-nowStream__card-text">
                <p>{{ item.title }}</p>
                <div class="app-nowStream__card-button">Перейти к статье</div>
              </div>
            </swiper-slide>
          </swiper-container>
          <div class="app-nowStream__arrows">
            <img class="app-nowStream__arrows-left" src="/public/стрелка лева.png" alt="" />
            <img class="app-nowStream__arrows-right" src="/public/стрелка право.png" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.swiper {
  padding: 200px;
}
.app-nowStream__container {
  width: 100%;
  max-width: 1176px;
  margin: 0 auto;
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
  z-index: 10;
}

.app-nowStream__arrows-right {
  position: absolute;
  top: 50%;
  right: 0;
  cursor: pointer;
  z-index: 10;
}

@media (max-width: 1300px) {
  .app-nowStream__cards {
    max-width: calc(272px * 4 + 30px * 3);
  }
}

@media (max-width: 1260px) {
  .app-nowStream__cards {
    max-width: calc(272px * 3 + 30px * 2);
  }
}

@media (max-width: 960px) {
  .app-nowStream__cards {
    max-width: calc(272px * 2 + 30px * 1);
  }
}

@media (max-width: 660px) {
  .app-nowStream__cards {
    max-width: 277px;
  }
}

.app-nowStream__card {
  display: flex;
  flex-direction: column;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 1), rgba(7, 168, 219, 0.1));
  overflow: hidden;
  height: 400px;
  width: 272px !important;
  border-radius: 5px;
  box-shadow: 0px 0px 5px 0px rgba(102, 102, 102, 0.7);
  border: 2px solid #fff;
  flex-shrink: 0;
  margin-bottom: 5px;
  margin-top: 5px;
}

.app-nowStream__card img {
  width: 100%;

  display: block;
}

.app-nowStream__card-text {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 25px;
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
