<template>
  <div class="app-practice__section">
    <div class="app-gendalf__container">
      <div class="app-practice">
        <h2>Ты студент и хочешь устроиться на практику?</h2>
        <div class="app-practice__button">Оставить заявку</div>
      </div>
    </div>
  </div>
</template>

<style>
.app-practice__section {
  position: relative;
  width: 100%;
  height: 415px;
  background-image: url('/value/VectorFon.jpg');
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.app-practice__section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 47, 61, 0.5);
  z-index: 1;
}

.app-practice {
  align-items: center;
  display: flex;
  justify-content: center;
  flex-direction: column;
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

.app-practice > h2 {
  max-width: 800px;
  font-weight: 700;
  font-size: 36px;
  margin-bottom: 20px;
}

.app-practice__button {
  width: 100%;
  max-width: 289px;
  border-radius: 5px;
  padding: 13px 13px;
  background-color: rgba(155, 204, 55, 1);
  color: #fff;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 1px solid rgba(155, 204, 55, 1);
}

.app-practice__button:hover {
  color: rgba(155, 204, 55, 1);
  background-color: white;
}
</style>
