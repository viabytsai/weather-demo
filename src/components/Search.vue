<template>
  <input type="text"
         :value="$store.state.search"
         @change="onchange">
  <span>城市:{{$store.getters.searchText}}</span>
</template>

<script>
export default {
  methods:{
    onchange(e){
      this.$store.commit('setSearch',e.target.value)
      this.$store.dispatch('getWeather',e.target.value)
    }
  }
}
</script>

