<template>
  <div class="app-MainTitle__section">
    <div class="app-gendalf__container">
      <div class="app-MainTitle__containerFlex">
        <div class="app-MainTitle">
          <h1>Добро пожаловать в ГЭНДАЛЬФ!</h1>
          <p>
            Мы готовы поделиться секретом, почему любим компанию, в которой работаем. Если тебе
            будут близки наши ценности и идеи, то смело записывайся на собеседование!
          </p>
          <div class="app-MainTitle__buttons">
            <div class="app-MainTitle__why-us">Почему мы</div>
            <div class="app-MainTitle__sign-up">Записаться на собеседование</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.app-MainTitle__section {
  position: relative;
  width: 100%;
  height: 565px;
  background-image: url('/menu/GendalfOffice.png');
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 50px;
}

.app-MainTitle__section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 47, 61, 0.77);
  z-index: 1;
}

.app-MainTitle {
  width: 100%;
  max-width: 780px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
  text-align: center;
  color: #fff;
}

.app-MainTitle_container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.app-MainTitle > h1 {
  max-width: 660px;
  font-weight: 700;
  font-size: 64px;
  margin: 0 auto 20px auto;
}

.app-MainTitle > p {
  max-width: 834px;
  font-weight: 400;
  font-size: 25px;
  margin-bottom: 42px;
}

.app-MainTitle__buttons {
}

.app-MainTitle__why-us {
  display: inline-block;
  border-radius: 5px;
  padding: 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  max-width: 175px;
  width: 100%;
  margin-right: 63px;
  transition: all 0.3s ease;
  border: 1px solid rgba(155, 204, 55, 1);
}

.app-MainTitle__sign-up {
  display: inline-block;
  border-radius: 5px;
  padding: 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  max-width: 327px;
  width: 100%;
  transition: all 0.3s ease;
  border: 1px solid rgba(155, 204, 55, 1);
}

.app-MainTitle__why-us:hover,
.app-MainTitle__sign-up:hover {
  color: rgba(155, 204, 55, 1);
  background-color: white;
}

.app-MainTitle__containerFlex {
  display: flex;
  justify-content: center;
  align-items: center;
}

@media (max-width: 768px) {
  .app-MainTitle__section {
    height: 378px;
  }
  .app-MainTitle > h1 {
    font-size: 24px;
  }
  .app-MainTitle > p {
    font-size: 16px;
  }
  .app-MainTitle__buttons {
    display: block;
    width: 100%;
    max-width: 295px;
    margin: 0 auto;
  }

  .app-MainTitle__why-us {
    display: block;
    margin-right: 0;
    width: 100%;
    max-width: 295px;
    margin-bottom: 10px;
  }

  .app-MainTitle__sign-up {
    display: block;
  }
}
</style>
