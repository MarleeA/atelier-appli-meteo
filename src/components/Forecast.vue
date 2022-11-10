<script>
export default {
  props: [
    "datetime",
    "city",
    "tempMax",
    "tempMin",
    "vitVent",
    "description",
    "icon",
  ],
};
</script>

<template>
  
  <div class="meteoCard">
    <h1>{{ city }}</h1>
    <img :src="`http://openweathermap.org/img/wn/${icon}@2x.png`" alt="" />
    <h2>{{ description }}</h2>
    <p>{{ datetime }}</p>
    <div>
      <div class="infos">
        <div class="temp-container">
          <h4>Températures</h4>
          <p>Min: {{ tempMin }}°C</p>
          <p>Max: {{ tempMax }}°C</p>
        </div>
        <div class="wind-container">
          <h4>Vitesse du vent</h4>
          <p>{{ vitVent }}km/h</p>
        </div>
      </div>

    </div>
  </div>
</template>

<!-- et l'icone -->

<style scoped>

*{
  /* font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif */
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.temp-container{
border-left: 1px solid black;
padding-left: 3px;
}
.wind-container{
  border-left: 1px solid black;
  border-right: 1px solid black;
  padding-right: 4px;
}

.meteoCard {
  margin: 15px;
  border: none;
  border-radius: 3%;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
  height:350px;
  padding-top: 0px;
  box-shadow: 4px 4px 4px  rgb(212, 211, 211);
  
}

img {
 
  width: 150px;
  height: 150px;
  margin-left: 50px;
}
.infos {
  display: flex;

}
h2{
  margin-top: 0px;
}
p,
h4 {
  margin: 0;
  
}
h4 {
  box-sizing: border-box;
  margin-bottom: 0.75rem;
  border-bottom: 1px solid black;
}

div:first-child {
  padding-right: 0.5rem;

}
div:last-child {
  padding-left: 0.5rem;
  
}
</style>
