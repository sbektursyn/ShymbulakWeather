<script>
import axios from 'axios';
export default {
  data(){
    return {
      isRight: true,
      today: '',
      humidity: '',
      now: '',
      hourly: '',
      hourlyValue: '',
      weatherData: null,
      currentTime: null,
      countHour: null,
      countHour2: null,
      countHour3: null,
      countHour4: null,
      countHour5: null,
      countHour6: null,
      countHour7: null,
      countSth: '',
      countSth2: '',
      countSth3: '',
      countSth4: '',
      countSth5: '',
      countSth6: '',
      countSth7: '',
      example: null,
      example2: null,
      example3: null,
      example4: null,
      example5: null,
      example6: null,
      example7: null,
    };
  },
  mounted() {
    this.getWeather();
    this.fetchWeatherData();
    this.updateTime();
  },
  methods: {
    menuOpen(){
      this.isRight = !this.isRight
    },
    getWeather() {
      
      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=Almaty&lang=ru&appid=33ea4cfd68c6b4051c16393b1be274f6&units=metric`)
        .then(response => {
          this.today = response.data.main.temp;
          this.today = Math.round(this.today);
          this.humidity = response.data.main.humidity;
          this.now = response.data.weather[0].description;
        })
        .catch(error => {
          console.log(error);
        });
      axios.get(`https://api.openweathermap.org/data/2.5/forecast?q=Almaty&appid=33ea4cfd68c6b4051c16393b1be274f6&units=metric`)
        .then(response => {
          this.hourly = response.data;
          this.hourlyValue = response.data.list[0].dt_txt;
          console.log(response.data)


          this.countHourly();

          if (this.countHour < 10) {
            this.countSth = '2023-06-08 ' + '0' + this.countHour + ':00:00';
          } else {
            this.countSth = '2023-06-08 ' + this.countHour + ':00:00';
          }

          if (this.countHour2 < 10) {
            this.countSth2 = '2023-06-08 ' + '0' + this.countHour2 + ':00:00';
          } else {
            this.countSth2 = '2023-06-08 ' + this.countHour2 + ':00:00';
          }

          if (this.countHour3 < 10) {
            this.countSth3 = '2023-06-09 ' + '0' + this.countHour3 + ':00:00';
          } else {
            this.countSth3 = '2023-06-09 ' + this.countHour3 + ':00:00';
          }

          if (this.countHour4 < 10) {
            this.countSth4 = '2023-06-09 ' + '0' + this.countHour4 + ':00:00';
          } else {
            this.countSth4 = '2023-06-09 ' + this.countHour4 + ':00:00';
          }

          if (this.countHour5 < 10) {
            this.countSth5 = '2023-06-09 ' + '0' + this.countHour5 + ':00:00';
          } else {
            this.countSth5 = '2023-06-09 ' + this.countHour5 + ':00:00';
          }

          if (this.countHour6 < 10) {
            this.countSth6 = '2023-06-09 ' + '0' + this.countHour6 + ':00:00';
          } else {
            this.countSth6 = '2023-06-09 ' + this.countHour6 + ':00:00';
          }

          if (this.countHour7 < 10) {
            this.countSth7 = '2023-06-09 ' + '0' + this.countHour7 + ':00:00';
          } else {
            this.countSth7 = '2023-06-09 ' + this.countHour7 + ':00:00';
          }

          var countSth = this.countSth;
          var countSth2 = this.countSth2;
          var countSth3 = this.countSth3;
          var countSth4 = this.countSth4;
          var countSth5 = this.countSt5h;
          var countSth6 = this.countSth6;
          var countSth7 = this.countSth7;
          var hourlyList = this.hourly.list;

          for (var i = 0; i < 30; i++) {
            if (countSth == hourlyList[i].dt_txt) {
              this.example = this.hourly.list[i].main.temp
              this.example = Math.round(this.example);
            } else if (countSth2 == hourlyList[i].dt_txt){
              this.example2 = this.hourly.list[i].main.temp
              this.example2 = Math.round(this.example2);
            } else if (countSth3 == hourlyList[i].dt_txt){
              this.example3 = this.hourly.list[i].main.temp
              this.example3 = Math.round(this.example3);
            } else if (countSth4 == hourlyList[i].dt_txt){
              this.example4 = this.hourly.list[i].main.temp
              this.example4 = Math.round(this.example4);
            } else if (countSth5 == hourlyList[i].dt_txt){
              this.example5 = this.hourly.list[i].main.temp
              this.example5 = Math.round(this.example5);
            } else if (countSth6 == hourlyList[i].dt_txt){
              this.example6 = this.hourly.list[i].main.temp
              this.example6 = Math.round(this.example6);
            } else if (countSth7 == hourlyList[i].dt_txt){
              this.example7 = this.hourly.list[i].main.temp
              this.example7 = Math.round(this.example7);
            }
          }




        })
        .catch(error => {
          console.log(error);
        });
    },
    fetchWeatherData() {
      const apiKey = '967bce65ce664cc592ae4619c72d28e5';
      const apiUrl = 'https://api.weatherbit.io/v2.0/forecast/hourly?city=Almaty&key=967bce65ce664cc592ae4619c72d28e5';

      axios.get(apiUrl, {
        params: {
          key: apiKey,
          city: 'Almaty'
        }
      })
      .then(response => {
        this.weatherData = response.data;
        console.log(this.weatherData)







      })
      .catch(error => {
        console.error(error);
      });

    },
    updateTime() {
      const date = new Date();
      const hours = String(date.getHours()).padStart(2, '0');
      this.currentTime = `${hours}`;

      setTimeout(this.updateTime, 1000);
    },
    countHourly() {
      this.countHour = Number(this.currentTime) 
      if (this.countHour == 24){
        this.countHour = 0
      } else if (this.countHour > 24) {
        this.countHour = this.countHour - 24
      }


      this.countHour2 = this.countHour +3

      if (this.countHour2 == 24){
        this.countHour2 = 0
      } else if (this.countHour2 > 24) {
        this.countHour2 = this.countHour2 - 24
      } 

      this.countHour3 = this.countHour2 +3

      if (this.countHour3 == 24){
        this.countHour3 = 0
      } else if (this.countHour3 > 24) {
        this.countHour3 = this.countHour3 - 24
      } 



      this.countHour4 = this.countHour3 +3

      if (this.countHour4 == 24){
        this.countHour4 = 0
      } else if (this.countHour4 > 24) {
        this.countHour4 = this.countHour4 - 24
      }



      this.countHour5 = this.countHour4 +3

      if (this.countHour5 == 24){
        this.countHour5 = 0
      } else if (this.countHour5 > 24) {
        this.countHour5 = this.countHour5 - 24
      }



      this.countHour6 = this.countHour5 +3

      if (this.countHour6 == 24){
        this.countHour6 = 0
      } else if (this.countHour6 > 24) {
        this.countHour6 = this.countHour6 - 24
      }




      this.countHour7 = this.countHour6 +3

      if (this.countHour7 == 24){
        this.countHour7 = 0
      } else if (this.countHour7 > 24) {
        this.countHour7 = this.countHour7 - 24
      }


      console.log(this.countHour)
    }
  }
}
</script>
<template>
  <header class="header w-full h-16 flex p-4">
    <div>
      <button @click="menuOpen" class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/menu.png"></button>
      <button class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/find.png"></button>
    </div>
    <img class="h-10" src="./img/logo.jpg">
    <div>
      <button class="w-10 h-10 headerBtn"><img class="menuImg" src="./img/user.png"></button>
      <button class="w-10 h-10 headerBtn heart"><img class="menuImg" src="./img/vector.png"></button>
      <button class="w-10 h-10 headerBtn"><img class="menuImg2" src="./img/vec.png"></button>
    </div>
  </header>
  <div :class="{ active: isRight }" class="nav w-72 absolute bg-white min-h-100%">
    <button class="navBtn"><img class="navInfoImg" src="./img/home.png">Главная</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/funic.png">Билеты</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/glasses.png">Прокат</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Школа</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Развлечения</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Отель</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Рестораны</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Магазины</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Детям</button>
    <button class="navBtn"><img class="navInfoImg" src="./img/">Паркинг</button>
    <button class="navBtn2"><img class="navInfoImg" src="./img/info.png">info</button>
  </div>
  <div class="mainContent">
    <b>Погода</b>
    <div class="cards">
      <div class="card today bg-sky-300 min-h-100 flex">
        <div class="todayWeather">
          
        </div>
        <div class="todayWeatherNum flex flex-col">
          <div class="h-1/2 flex p-4">
            {{today}}°C
          </div>
          <div class="todayDescription">
            {{now}}
            <p class="todayDescriptionText">Сейчас</p>
          </div>
        </div>
      </div>
      <div class="card hourly bg-sky-300 min-h-100 flex flex-col">
        <div class="flex nameHourly">
          <img class="clockImg" src="./img/clock.png">Погода в течение дня
        </div>
        <div class="flex hourlyContent min-w-100">

  <!-- -------------------------------------------------------------------------------------------------------------------------------- -->



          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour2 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example2 }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour3 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example3 }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour4 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example4 }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour5 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example5 }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour6 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example6 }}</p>
          </div>
          <div class="hourlyCon flex flex-col">
            <p class="textHourly2">{{ countHour7 }}</p>
            <img class="hourlyImg" src="./img/sun.png">
            <p class="textHourly">{{ example7 }}</p>
          </div>





  <!-- -------------------------------------------------------------------------------------------------------------------------------- -->
        </div>
      </div>
    </div>
    <div class="soon bg-sky-300 w-full min-h-100">

    </div>
  </div>
  <footer class="w-full min-h-100">
    <img class="shymImg" src="./img/shym.png">

    <div class="services">
      <div>
        <p class="text-white mt-8 title">Курорт</p>
        <div class="flex isFlex">
          <div class="w-1/2 ul flex flex-col">
            <p>Отели</p>
            <p>Рестораны</p>
            <p>Магазины</p>
          </div>
          <div class="ul0 flex flex-col">
            <p>Развлечения</p>
            <p>Детям</p>
          </div>
        </div>
      </div>
      
      <div>
        <p class="text-white mt-8 title">Катания</p>
        <div class="flex isFlex">
          <div class="w-1/2 ul flex flex-col">
            <p>Билеты</p>
            <p>Прокат</p>
          </div>
          <div class="ul0 flex flex-col">
            <p>Школа</p>
            <p>Паркинг</p>
          </div>
        </div>
      </div>
      
      <div>
        <p class="text-white mt-8 title">Инфо</p>
        <div class="flex isFlex">
          <div class="w-1/2 ul flex flex-col">
            <p>Правила курорта</p>
            <p>Новости</p>
          </div>
          <div class="ul0 flex flex-col">
            <p>Как добраться</p>
            <p class="w-16">Техническая поддержка</p>
          </div>
        </div>  
      </div>

      <div>
        <p class="text-white mt-8 title">Контакты</p>
        <div class="flex isFlex">
          <div class="w-1/2 ul flex flex-col">
            <p class="flex"><img class="sources" src="./img/facebook.png"><img class="sources" src="./img/youtube.png"><img class="sources" src="./img/insta.png"><img class="sources" src="./img/vk.png"></p>
            <p>info@shymbulak.com</p>
            <p>+7 727 331 77 77</p>
          </div>
        </div>  
      </div>
    </div>
    <img class="google" src="./img/google.png">
    <img class="appStore" src="./img/appStore.png">
  </footer>
</template>
<style>
.hourlyCon {
  margin: 0 8px;
  padding: 0;
  width: 44px;
  height: 90px;
  align-items: center;
}
.textHourly {
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
  text-align: center;
  color: #4F5864;
  padding-top: 0;
}
.textHourly2 {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  color: #6D7784;
}
.hourlyImg {
  width: 24px;
  height: 24px;
}
.nav {
  padding: 20px 0 30px 60px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: flex-start;
}
.navBtn {
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
  margin: 20px 0;
  display: flex;
  align-items: center;
}
.navInfoImg {
  width: 28px;
  height: 28px;
  margin-right: 10px;
}
.navBtn2 {
  color: white;
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
  margin: 20px 0;
  width: 136px;
  height: 48px;
  background: #75B6F2;
  box-shadow: 0px 8.88889px 10.6667px rgba(117, 182, 242, 0.15);
  border-radius: 12px;
  display: flex;
  padding: 10px 16px;
  align-items: center;
}
.hourlyContent {
  margin:14px 16px 0 16px;
  padding-bottom: 8px;
  overflow-x: auto;
  height: 90px;
}
.nameHourly {
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #4F5864;
  padding: 16px;
  margin: 0 16px;
  border-bottom: 1px solid #E1E7EE;;
}
.clockImg {
  width: 14px;
  height: 14px;
  margin-right: 8px;
}
.todayDescriptionText {
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #FFFFFF;
  padding-top: 8px;
}
.todayDescription {
  font-weight: 600;
  font-size: 21px;
  line-height: 25px;
  color: #FFFFFF;
  border-top: 1px solid rgba(255, 255, 255, 0.3);;
  padding: 4px 20px;

}
.todayWeatherNum {
  font-size: 48px;
  color: white;
  font-weight: 700;
  line-height: 58px;

  padding-right: 10px;
  width: 210px;
}
.todayWeather {
  width: 150px;
}
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
.ul0 {
  margin-top: 16px;
}
p {
  font-size: 16px;
  color: #A0A7AF;
  padding-top: 16px;
}
.google {
  margin-top: 40px;
  width: 180px;
}
.appStore {
  margin-top: 20px;
  width: 156px;
}
.sources {
  width: 32px;
  height: 32px;
  margin-right: 12px;
}
.active {
  right: 100%;
}




@media screen and (min-width: 468px) {
  .soon {
    height: 225px;
  }
}
@media screen and (min-width: 768px) {
  .shymImg {
    width: 117px;
  }
  .title {
    font-size: 18px;
  }
  .ul {
    margin-top: 16px;
  }
  .ul0 {
    margin-top: 0px;
  }
  p {
    font-size: 16px;
    color: #A0A7AF;
    padding-top: 16px;
  }
  .google {
    margin-top: 40px;
    width: 180px;
  }
  .appStore {
    margin-top: 20px;
    width: 156px;
  }
  .services {
    display: flex;
    justify-content: space-between;
  }
  .isFlex {
    flex-direction: column;
  }
  .sources {
    width: 32px;
    height: 32px;
  }
}
@media screen and (max-width: 768px) {
  .heart {
    display: none;
  }
}





</style>