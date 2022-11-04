<script>
export default {
  props: ['city','tempMax', 'tempMin', 'vitVent', 'description','icon'],
};
</script>

<template>
  <div class="meteoCard">
    <h1>{{city}}</h1>
    <img :src="`http://openweathermap.org/img/wn/${icon}@2x.png`" alt="">
    <h2>{{description}}</h2>
    <p>Date: {{ }}</p>
    <p>Température min: {{tempMin}}°C</p>
    <p>Température max: {{tempMax}}°C</p>
    <p>Vitesse du vent: {{vitVent}}</p>
    
  </div>
</template>

<!-- et l'icone --> 

<style scoped>
.meteoCard {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 250px;
  height: 350px;
  border: solid 1px grey;
  border-radius: 20px;
  text-align:center;
  font-size: 18px;
  padding: 20px;

}
img{
  
  width: 100px;
  height: 100px;
  margin-left: 50px;
  
}
</style>
