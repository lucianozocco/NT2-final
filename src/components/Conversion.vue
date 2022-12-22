<template>
    <div>
      <h2>Conversor de Temperatura</h2>
      <p>Ingrese Temperatura °C <input type="text" v-model="tempC" ></p>

      <p>
        Conv Temperatura °F: <span :style="{color: analizarTemperatura.color}">{{ convertirTemp.valorF }}</span>
      </p>
      <p>
        Conv Temperatura °K: <span :style="{color: analizarTemperatura.color}"> {{ convertirTemp.valorK }} </span>
      </p>

      <p>{{"respuestas: 1:c, 2:b, 3:c, 4:a, 5:b"}}</p>

  </div>
  



</template>

<script>
export default {
  name: 'Conv',
  props: {
  },
  mounted() {
  },
  data() {
    return {
      tempC : 0,
    }
  },
  methods : {
  },
  computed : {
    convertirTemp() {
      return {
        valorF: ((this.tempC * 1.8) + 32),
        valorK: (this.tempC + 273.15)
      }
    },
    analizarTemperatura() {
        let color;
        const TOPE1 = 0;
        const TOPE2 = 15;

        if (this.tempC <= TOPE1) {
          color = 'blue';
        } else if (this.tempC > TOPE1 && this.tempC < TOPE2) {
            color = 'magenta';
          } else if (this.tempC >= TOPE2) {
            color = 'red';
        } 
        return {
          color
        }
      }
  }
}
</script>

<style scoped>

</style>
