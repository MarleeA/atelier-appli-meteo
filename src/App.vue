<script setup>
import  Forecast from './components/Forecast.vue';
</script>

<script>
const apiKey = "f354617bca59ded0ad175d1fb6426bc7";

// window.fetch('http://api.openweathermap.org/data/2.5/weather?lat=43.296482&lon=5.36978&lang=fr&units=metric&appid=f354617bca59ded0ad175d1fb6426bc7')

// .then(res => res.json())
// .then(resJson => console.log(resJson))


export default {
  data () {
    return{
      datetime:"",
      city:"",
      tempMax:"",
      tempMin:"",
      vitVent:"",
      description:"",
      icon:""
    }
  },
mounted : async function(){
//   window.fetch('http://api.openweathermap.org/data/2.5/weather?lat=43.296482&lon=5.36978&lang=fr&units=metric&appid=f354617bca59ded0ad175d1fb6426bc7')

// .then(res => res.json())
// .then(resJson => console.log(resJson.main.temp_min))

const res = await fetch('http://api.openweathermap.org/data/2.5/weather?lat=43.296482&lon=5.36978&lang=fr&units=metric&appid=f354617bca59ded0ad175d1fb6426bc7')
const json = await res.json()
console.log(json);
this.city= json.name
console.log(json.name);

this.tempMin= json.main.temp_min
console.log(json.main.temp_min);

this.tempMax= json.main.temp_max
console.log(json.main.temp_max);

this.vitVent= json.wind.speed
console.log(json.wind.speed);

this.description= json.weather[0].description
console.log(json.weather[0].description);

this.icon= json.weather[0].icon
}
}

</script>

<template>
  <header>
    <h1>Application météo</h1>
  </header>

  <div>
   <Forecast 
   :city= this.city 
   :tempMax= this.tempMax 
   :tempMin= this.tempMin 
   :vitVent= this.vitVent 
   :description= this.description 
   :icon= this.icon /> 
  </div>
 
</template>

<style scoped>
header{
  width: 100%;
  flex-direction: column;
}
</style>
