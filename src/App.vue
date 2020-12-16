<template>
  <div id="app">
    <calendar :datas="aulas"></calendar>
  </div>
</template>

<script>

import Calendar from './components/calendar/Calendar.vue';

export default {
  name: 'app',

  components: {
    'calendar' : Calendar
  },

  data () {
    return {
      aulas: []
    }
  },

  created() {

    let promise = this.$http.get('http://localhost:3000/aulas');
    
    promise
      .then(res => res.json())
      .then(aulas => this.aulas = aulas);
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
