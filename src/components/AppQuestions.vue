<template>
  <div class="app-questions__section">
    <div class="app-gendalf__container">
      <div class="app-questions">
        <div class="app-questions__content">
          <h2>Остались вопросы?</h2>
          <div v-for="(item, index) in items" :key="index" class="app-questions__item">
            <div class="app-questions__item-title" @click="toggleExpand(index)">
              <img
                :src="item.img"
                alt=""
                :style="{ transform: item.isExpanded ? 'rotate(-90deg)' : 'rotate(0deg)' }"
              />
              <p
                class="app-questions__item-title-text"
                :class="{ 'app-questions__item-title-text--active': item.isExpanded }"
              >
                {{ item.title }}
              </p>
            </div>

            <div class="app-questions__item-text job-content">
              <p>{{ item.textBeginning }}</p>
              <ul>
                <li>
                  <span class="app-questions__item-span">{{ item.textMiddleSpan }}</span>
                  {{ item.textMiddle }}
                </li>
                <li>
                  <span class="app-questions__item-span">{{ item.textEndSpan }}</span>
                  {{ item.textEnd }}
                </li>
                <li>
                  <span class="app-questions__item-span">{{ item.textFooterSpan }}</span>
                  {{ item.textFooter }}
                </li>
              </ul>
            </div>
          </div>
        </div>
        <img src="/public/Group 170.png" alt="" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-questions__section {
  padding: 40px 0;
  background: linear-gradient(
    to right,
    rgba(40, 228, 115, 0.16),
    rgba(70, 205, 22, 0.14),
    rgba(39, 221, 209, 0.39),
    rgba(5, 176, 213, 0.32)
  );
}

.app-questions__content {
  max-width: 776px;
}

.app-questions {
  position: relative;
}

.app-questions > img {
  position: absolute;
  top: -20px;
  right: -5px;
}

.app-gendalf__container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.app-questions__content > h2 {
  font-weight: 700;
  font-size: 26px;
  color: rgba(0, 183, 236, 1);
  margin-bottom: 46px;
}

.app-questions__item {
  margin-bottom: 20px;
}

.app-questions__item-title {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 8px;
  cursor: pointer;
  position: relative;
  padding-right: 30px;
}

.app-questions__item-title img {
  width: 24px;
  height: 24px;
  transition: transform 0.3s ease;
}

.app-questions__item-title-text {
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  text-decoration: underline;
  margin: 0;
}

.app-questions__item-title-text--active {
  font-weight: 400;
  font-size: 18px;
  color: rgba(0, 183, 236, 1);
  text-decoration: underline;
  margin: 0;
}

.toggle-icon {
  position: absolute;
  right: 0;
  font-size: 24px;
  font-weight: bold;
  color: rgba(0, 183, 236, 1);
  transition: transform 0.3s ease;
}

.app-questions__item-text {
  overflow: hidden;
  height: 80px;
  transition: height 0.3s ease;
  margin-left: 40px;
}

.app-questions__item-text p {
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  margin-bottom: 10px;
}

.app-questions__item-text ul {
  padding-left: 20px;
}

.app-questions__item-text li {
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
  margin-bottom: 10px;
  list-style-type: disc;
}

.app-questions__item-span {
  color: rgb(75, 75, 75);
  font-weight: 700;
}

@media (max-width: 768px) {
  .app-questions > img {
    display: none;
  }
}
</style>

<script>
import { defineComponent, ref, onMounted, nextTick } from 'vue'

export default defineComponent({
  setup() {
    const items = ref([
      {
        img: 'menu/arrow.png',
        title: 'На что нужно обратить внимание на собеседовании?',
        textBeginning:
          'Кроме умения представлять себя, грамотно разговаривать и опрятного внешнего вида, стоит обратить внимание еще на пару моментов. Они не очевидны, но очень эффективны.',
        textMiddle:
          'Конечно, собеседование – это стрессовая ситуация, которая мешает конструктивно мыслить. Если волнение берет верх – выпейте немного воды, прижмите стопы к полу, а главное, помните: ничего ужасного произойти не может.',
        textMiddleSpan: 'Сохраняйте спокойствие.',
        textEnd:
          'Если собеседование – пьеса, вы – ее главный герой. Подготовьте рассказ о себе заранее, опираясь на важные навыки, и опишите, почему это важно для данной работы. Все это придаст вам уверенности в себе.',
        textEndSpan: 'Внимание к самопрезентации.',
        textFooter:
          'Если вам задали какой-либо вопрос, который кажется вам сложным или задевает личные качества, знайте – правильных ответов не существует. Каверзные вопросы призваны показать вашу стрессоустойчивость и умение ориентироваться в ситуации. Здесь поможет адекватная самокритика и знания в своей профессии.',
        textFooterSpan: 'Каверзные вопросы – это норма.',
        isExpanded: false,
      },
      {
        img: 'menu/arrow.png',
        title: 'Как правильно составить резюме?',
        textBeginning:
          'Кроме умения представлять себя, грамотно разговаривать и опрятного внешнего вида, стоит обратить внимание еще на пару моментов. Они не очевидны, но очень эффективны.',
        textMiddle:
          'Конечно, собеседование – это стрессовая ситуация, которая мешает конструктивно мыслить. Если волнение берет верх – выпейте немного воды, прижмите стопы к полу, а главное, помните: ничего ужасного произойти не может.',
        textMiddleSpan: 'Сохраняйте спокойствие.',
        textEnd:
          'Если собеседование – пьеса, вы – ее главный герой. Подготовьте рассказ о себе заранее, опираясь на важные навыки, и опишите, почему это важно для данной работы. Все это придаст вам уверенности в себе.',
        textEndSpan: 'Внимание к самопрезентации.',
        textFooter:
          'Если вам задали какой-либо вопрос, который кажется вам сложным или задевает личные качества, знайте – правильных ответов не существует. Каверзные вопросы призваны показать вашу стрессоустойчивость и умение ориентироваться в ситуации. Здесь поможет адекватная самокритика и знания в своей профессии.',
        textFooterSpan: 'Каверзные вопросы – это норма.',
        isExpanded: false,
      },
      {
        img: 'menu/arrow.png',
        title: 'Возможно ли устроиться без опыта?',
        textBeginning:
          'Кроме умения представлять себя, грамотно разговаривать и опрятного внешнего вида, стоит обратить внимание еще на пару моментов. Они не очевидны, но очень эффективны.',
        textMiddle:
          'Конечно, собеседование – это стрессовая ситуация, которая мешает конструктивно мыслить. Если волнение берет верх – выпейте немного воды, прижмите стопы к полу, а главное, помните: ничего ужасного произойти не может.',
        textMiddleSpan: 'Сохраняйте спокойствие.',
        textEnd:
          'Если собеседование – пьеса, вы – ее главный герой. Подготовьте рассказ о себе заранее, опираясь на важные навыки, и опишите, почему это важно для данной работы. Все это придаст вам уверенности в себе.',
        textEndSpan: 'Внимание к самопрезентации.',
        textFooter:
          'Если вам задали какой-либо вопрос, который кажется вам сложным или задевает личные качества, знайте – правильных ответов не существует. Каверзные вопросы призваны показать вашу стрессоустойчивость и умение ориентироваться в ситуации. Здесь поможет адекватная самокритика и знания в своей профессии.',
        textFooterSpan: 'Каверзные вопросы – это норма.',
        isExpanded: false,
      },
      {
        img: 'menu/arrow.png',
        title: 'Ошибки на собеседовании. Чего нужно избегать?',
        textBeginning:
          'Кроме умения представлять себя, грамотно разговаривать и опрятного внешнего вида, стоит обратить внимание еще на пару моментов. Они не очевидны, но очень эффективны.',
        textMiddle:
          'Конечно, собеседование – это стрессовая ситуация, которая мешает конструктивно мыслить. Если волнение берет верх – выпейте немного воды, прижмите стопы к полу, а главное, помните: ничего ужасного произойти не может.',
        textMiddleSpan: 'Сохраняйте спокойствие.',
        textEnd:
          'Если собеседование – пьеса, вы – ее главный герой. Подготовьте рассказ о себе заранее, опираясь на важные навыки, и опишите, почему это важно для данной работы. Все это придаст вам уверенности в себе.',
        textEndSpan: 'Внимание к самопрезентации.',
        textFooter:
          'Если вам задали какой-либо вопрос, который кажется вам сложным или задевает личные качества, знайте – правильных ответов не существует. Каверзные вопросы призваны показать вашу стрессоустойчивость и умение ориентироваться в ситуации. Здесь поможет адекватная самокритика и знания в своей профессии.',
        textFooterSpan: 'Каверзные вопросы – это норма.',
        isExpanded: false,
      },
    ])

    const toggleExpand = (index) => {
      const item = items.value[index]
      item.isExpanded = !item.isExpanded

      nextTick(() => {
        const content = document.querySelectorAll('.job-content')[index]
        if (item.isExpanded) {
          content.style.height = content.scrollHeight + 'px'
        } else {
          content.style.height = '2px'
        }
      })
    }

    onMounted(() => {
      document.querySelectorAll('.job-content').forEach((content) => {
        content.style.height = '2px'
        content.style.transition = 'height 0.3s ease'
      })
    })

    return {
      items,
      toggleExpand,
    }
  },
})
</script>
