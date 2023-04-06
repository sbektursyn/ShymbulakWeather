<script >
</script>

<template>
  <div class="menu flex flex-col fixed">
    <button class="menuOpen mt-8 mr-36">=</button>

    <div class="flex flex-col m-8">
      <button class="menuElements"><img src="">Главная</button>

      <button class="menuElements"><img src="">Билеты</button>

      <button class="menuElements"><img src="">Прокат</button>

      <button class="menuElements"><img src="">Школа</button>

      <button class="menuElements"><img src="">Развлечение</button>

      <button class="menuElements"><img src="">Отель</button>

      <button class="menuElements"><img src="">Ресторан</button>

      <button class="menuElements"><img src="">Магазин</button>

      <button class="menuElements"><img src="">Детям</button>
    </div>

    <button class="menuInfo">Инфо</button>
  </div>

  <div class="mainWindow">
    <div class="header flex">
      <img src="./logo.jpg" class="logo">
    </div>
    <div class="Window">
      <b class="text-4xl">Погода</b>
      <div class="cards">
        <div class="card"></div>
        <div class="card2"></div>
      </div>
      <div class="card3"></div>
    </div>
  </div>

  <footer class="text-white flex flex-col">
    <div class="up flex">
      <div class="footerIn0">
        <img class="shymFooterImg" src="./shym.png">
        <img class="google" src="./google.png">
        <img class="appStore" src="./appStore.png">
      </div>
      <div class="footerIn flex flex-col ml-96">
        <b class="between">Курорт</b>
        <p class="between2 betweenColor">Отели</p>
        <p class="between betweenColor">Рестораны</p>
        <p class="between betweenColor">Развлечения</p>
        <p class="between betweenColor">Магазин</p>
        <p class="between betweenColor">Детям</p>
      </div>
      <div class="footerIn flex flex-col ml-16">
        <b class="between">Катания</b>
        <p class="between2 betweenColor">Билеты</p>
        <p class="between betweenColor">Прокат</p>
        <p class="between betweenColor">Школа</p>
        <p class="between betweenColor">Паркинг</p>
      </div>
      <div class="footerIn flex flex-col ml-16">
        <b class="between">Инфо</b>
        <p class="between2 betweenColor">Погода</p>
        <p class="between betweenColor">Правила</p>
        <p class="between betweenColor">Новости</p>
        <p class="between betweenColor">Как добраться</p>
        <p class="between betweenColor">Тех. поддержка</p>
      </div>
      <div class="footerIn3 flex flex-col ml-16">
        <b class="between">Контакты</b>
        <p class="between2 betweenColor">ссылки на соцсети</p>
        <p class="between betweenColor">info@shymbulak.com</p>
        <p class="between betweenColor">+7 727 331 77 77</p>
      </div>
    </div>
    
    <div class="under">
      <p>© 2022 ТОО «Chimbulak Development»</p>
    </div>

  </footer>
</template>

<style>
.under {
  width: 1296px;
  margin-top: 70px;
  padding-top: 20px;
  border-top: 1px solid #4F5864;
  color: #4F5864;
}
.betweenColor{
  color: #A0A7AF;
}
.menu {
  width: 300px;
  height: 1080px;
  border-right: 2px solid #DAE9F4;
}
.mainWindow {
  width: 1620px;
  position: absolute;
  width: 1620px;
  height: 944px;
  left: 300px;
  top: 0px;
}
.header {
  flex-wrap: ;
  position: absolute;
  width: 1620px;
  right: 0%;
  top: 0%;
  bottom: 93.17%;
}
.menuElements {
  font-family: Inter;
  font-size: 18px;
  font-weight: 500;
  line-height: 22px;
  letter-spacing: 0em;
  text-align: left;

  margin: 20px;
}
.Window {
  position: absolute;
  top: 6.83%;
  width: 1620px;
  height: 900px;
  padding: 50px;
  padding-left: 162px;
  padding-right: 162px;
}
.cards {
  margin-top: 30px;
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(636px, 1fr));
  gap: 20px;
}
.card {
  height: 256px;
  background-color: #75B6F2;
  border-radius: 20px;
}
.card2 {
  height: 256px;
  box-sizing: border-box;
  border: 1px solid #F3F5F7;
  border-radius: 20px;
}
.card3 {
  margin-top: 30px;
  width: 1296px;
  height: 328px;
  background: #F4F8FD;
  border-radius: 20px;
}
footer {
  position: absolute;
  width: 1620px;
  height: 438px;
  left: 300px;
  top: 944px;
  background: #212225;
  padding-left: 162px;
  padding-top: 50px;
}
.shymFooterImg {
  width: 158px;
}
.google {
  width: 158px;
  margin-top: 120px;
}
.appStore {
  width: 138px;
  margin-top: 17px;
}
.logo {
  width: 50px;
  margin-left: 46px;
}
.footerIn0 {
  width: 180px;
}
.footerIn {
  width: 120px;
}
.footerIn3 {
  width: 200px;
}
.between {
  padding-top: 15px;
}
.between2 {
  padding-top: 30px;
}
</style>
