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
        <div>
          <h4>Températures</h4>
          <p>Min: {{ tempMin }}°C</p>
          <p>Max: {{ tempMax }}°C</p>
        </div>
        <div>
          <h4>Vitesse du vent</h4>
          <p>{{ vitVent }}km/h</p>
        </div>
      </div>

    </div>
  </div>
</template>

<!-- et l'icone -->

<style scoped>

.meteoCard {
  margin: 15px;
  border: 1px solid black;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  height: fit-content;
  
}
p:first-child {
  margin: 0;
  padding: 1rem;
}
img {
  width: 100px;
  height: 100px;
  margin-left: 50px;
}
img {
  width: 100px;
  height: 100px;
}
.infos {
  display: flex;
  border-left: 1px solid black;
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
  border-right: 1px solid black;
}
div:last-child {
  padding-left: 0.5rem;
  
}
</style>
