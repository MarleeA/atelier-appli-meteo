<script>
export default {
  props: ['datetime','city','tempMax', 'tempMin', 'vitVent', 'description','icon'],
};
</script>

<template>
  <div class="meteoCard">
    <h1>{{city}}</h1>
    <img :src="`http://openweathermap.org/img/wn/${icon}@2x.png`" alt="">
    <h2>{{description}}</h2>
    <p>{{ datetime}}</p>
    <div>
      <h4>Températures</h4>
      <p>Min: {{tempMin}}°C</p>
      <p>Max: {{tempMax}}°C</p>

      <div>
        <h4>Vitesse du vent</h4>
        <p>{{vitVent}}km/h</p>
      </div>
    </div>
    
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
