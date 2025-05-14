<template>
  <div class="app-opportunities__section">
    <div class="app-gendalf__container">
      <div class="app-opportunities">
        <h2>Инфраструктура для твоего развития и роста</h2>
        <div class="app-opportunities__content">
          <p>
            Мы создаем платформу для профессионального развития каждого сотрудника. Главная цель –
            дать возможность учиться, работать и получать удовольствие от каждой успешной задачи. О
            возможностях личностного роста в ГЭНДАЛЬФ расскажет руководитель Департамента персонала
            и карьеры Татьяна Арсенович.
          </p>
          <div>
            <img src="/public/Видео.png" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.app-opportunities__section {
  background: linear-gradient(
    to right,
    rgba(40, 228, 115, 0.16),
    rgba(70, 205, 22, 0.14),
    rgba(39, 221, 209, 0.39),
    rgba(5, 176, 213, 0.32)
  );
  padding: 61px 0 60px 0;
  margin-bottom: 33px;
}

.app-opportunities > h2 {
  font-weight: 300;
  font-size: 36px;
  color: rgba(0, 183, 236, 1);
  margin-bottom: 43px;
  text-align: center;
}

.app-opportunities__content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.app-opportunities__content > p {
  max-width: 494px;
  font-weight: 400;
  font-size: 18px;
  color: rgba(102, 102, 102, 1);
}

@media (max-width: 768px) {
  .app-opportunities__content {
    flex-direction: column;
  }

  .app-opportunities__content > p {
    margin-bottom: 20px;
  }
}
</style>
