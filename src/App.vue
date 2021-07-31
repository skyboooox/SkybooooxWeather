<template>
  <div id="App">
    {{nowWeather}}
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      nowWeather: null
    }
  },
  mounted () {
    axios.get('https://api.caiyunapp.com/v2.5/KsCafVNa5pj08BbV/116.40717,39.90469/realtime.json')
      .then(nowWeatherGet => (
        this.nowWeather = nowWeatherGet
        // console.log(nowWeatherIcon)
      )).catch(error => (
        console.log(error)
      ))
  }
}
</script>

<style>
</style>
