<template>
  <div class="weather">
    <h2>{{searchText}} 天气详情</h2>
    <p>天气 {{weather.text}}</p>
    <p>体感温度 {{weather.feels_like}}</p>
    <p>风力 {{weather.wind_class}}</p>
    <button @click="setDefault">深圳天气</button>
  </div>
</template>

<script>
import { mapActions, mapGetters, mapMutations, mapState } from 'vuex'
export default {
  computed: {
    ...mapState(['search', 'weather']),
    ...mapGetters(['searchText'])
  },
  methods: {
    ...mapMutations(['setSearch']),
    ...mapActions(['getWeather']),
    setDefault() {
      this.setSearch('深圳')
      this.getWeather('深圳')
    }
  }
}
</script>

