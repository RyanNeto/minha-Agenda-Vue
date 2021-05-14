<template>
  <div>
    <Header/>
    <div id="container">
      <PainelContato/>
      <Agenda/>
    </div>
  </div>
</template>
  <script>
    import Agenda from './components/Agenda.vue'
    import PainelContato from './components/PainelContato.vue'
    import Header from './components/Header.vue'

  export default {
    name: 'App',
    components: {
    PainelContato, Header, Agenda,}
    }
</script>

<style>
body {
  margin: 0;
  background-color: #dddddd;
}
#container{
  display: flex;
  width: 100vw;
  justify-content: space-between;
  margin: auto;
}
</style>
