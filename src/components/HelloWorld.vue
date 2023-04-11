<script>
  
</script>
<template>
  <header class="header w-full h-16 flex p-4">
    <div>
      <button class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/menu.png"></button>
      <button class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/find.png"></button>
    </div>
    <img class="h-10" src="./img/logo.jpg">
    <div>
      <button class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/user.png"></button>
      <button class="w-10 h-10 headerBtn"><img class="menuImg2" src="./img/vec.png"></button>
    </div>
  </header>
  <div class="nav w-72 absolute bg-blue-300 min-h-100% right-full">
    hadsbkcjslkdnv
    <br>dvadvadv
    <br>advdavadv
    <br>advadv
  </div>
  <div class="mainContent">
    <b>Weather</b>
    <div class="cards">
      <div class="card today bg-sky-300 min-h-100"></div>
      <div class="card hourly bg-sky-300 min-h-100"></div>
    </div>
    <div class="soon bg-sky-300 w-full min-h-100"></div>
  </div>
  <footer class="w-full min-h-100">
    <img class="shymImg" src="./img/shym.png">
    <p class="text-white mt-8 title">Курорт</p>
    <div class="flex">
      <div class="w-1/2 ul flex flex-col">
        <p>Отели</p>
        <p>Рестораны</p>
        <p>Магазины</p>
      </div>
      <div class="ul flex flex-col">
        <p>Развлечения</p>
        <p>Детям</p>
      </div>
    </div>

    <p class="text-white mt-8 title">Катания</p>
    <div class="flex">
      <div class="w-1/2 ul flex flex-col">
        <p>Билеты</p>
        <p>Прокат</p>
      </div>
      <div class="ul flex flex-col">
        <p>Школа</p>
        <p>Паркинг</p>
      </div>
    </div>

    <p class="text-white mt-8 title">Инфо</p>
    <div class="flex">
      <div class="w-1/2 ul flex flex-col">
        <p>Правила курорта</p>
        <p>Новости</p>
      </div>
      <div class="ul flex flex-col">
        <p>Как добраться</p>
        <p>Техническая поддержка</p>
      </div>
    </div>



    <img class="google" src="./img/google.png">
  </footer>
</template>
<style>
.header {
  justify-content: space-between;
}
.menuImg {
  width: 24px;
  margin: 0 auto;
}
.menuImg2 {
  width: 20px;
  margin: 0 auto;
}
.headerBtn {
  margin: 0 6px;
  border: 1px solid #DAE9F4;
  border-radius: 6px;
}
.mainContent {
  padding: 16px;
}
.cards {
  margin-top: 24px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(208px, 2fr));
  gap: 20px;
}
.card {
  height: 168px;
  background-color: #4f82f9;
  border-radius: 16px;
}
.today {
  background: #75B6F2;
  box-shadow: 0px 8.88889px 10.6667px rgba(117, 182, 242, 0.15);
}
.hourly {
  background: #FFFFFF;
  box-shadow: 5px 5px 30px rgba(116, 142, 170, 0.12);
}
.soon {
  margin-top: 16px;
  border-radius: 16px;
  height: 501px;
  background: #F4F8FD;
}
footer {
  background: #212225;
  padding: 16px;
}
.shymImg {
  width: 117px;
}
.title {
  font-size: 18px;
}
.ul {
  margin-top: 16px;
}
p {
  font-size: 16px;
  color: #A0A7AF;
  padding-top: 16px;
}
.google {
  width: 180px;
}



@media screen and (min-width: 468px) {
  .soon {
    height: 225px;
  }
}



</style>