<script setup>
import  Forecast from './components/Forecast.vue';
</script>

<script>
const apiKey = "f354617bca59ded0ad175d1fb6426bc7";

window.fetch('http://api.openweathermap.org/data/2.5/weather?lat=43.296482&lon=5.36978&lang=fr&units=metric&appid=f354617bca59ded0ad175d1fb6426bc7')

.then(res => res.json())
.then(resJson => console.log(resJson))


export default {
  data () {
    return{
      listCards:[]
    }
  },
mounted : async function(){

const res = await fetch(`https://api.openweathermap.org/data/2.5/forecast?lat=43.1642&lon=5.2219&appid=${apiKey}&units=metric&lang=fr`)

const data = await res.json();
    this.listCards = data.list;
    console.log("listCards", this.listCards);

// this.tempMin= json.main.temp_min
// console.log(json.main.temp_min);

// this.tempMax= json.main.temp_max
// console.log(json.main.temp_max);

// this.vitVent= json.wind.speed
// console.log(json.wind.speed);

// this.description= json.weather[0].description
// console.log(json.weather[0].description);

// this.icon= json.weather[0].icon
}
}


</script>

<template>
  <header>
    <img src="@/assets/marseille3.png" id="logo" alt="">
  </header>

  <main>

    
     <Forecast 
     v-for="forecast in listCards"
        :description="forecast.weather[0].description"
        :vitVent="forecast.wind.speed"
        :tempMin="forecast.main.temp_min"
        :tempMax="forecast.main.temp_max"
        :datetime="forecast.dt_txt"
        :icon="forecast.weather[0].icon"
        :key="forecast.dt" /> 
  
  </main>

  <footer>&copy;Marlee Météo</footer>
 
</template>

<style scoped>

header,footer{

  height: 8rem;
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 0 1rem;
    background-color: rgb(106, 182, 198);
    color: white;
    
}

#logo{
  width: 400px;

}
main {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  display: flex;
  flex-direction: row;
  gap: 1rem;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
