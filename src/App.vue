<template>
  <!-- <ListItemComponent></ListItemComponent> -->
   <ListItemComponent :titluTask="titluTask1" />
   <ListItemComponent />

   <!-- v-model - legarea unei variabile a unui component cu un input -->
   <input type="text" v-model="titluTask1">
</template>

<script>
import ListItemComponent from './components/ListItemComponent';

export default {
  name: 'App',
  components: {
    ListItemComponent,
  },
  // Data - utilizata pentru crearea de date interne
  data() {
    return {
      titluTask1: 'Crearea unui proiect Vue cu TS'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

input {
  width:400px;
  height: 30px;
  font-size: 24px;
}
</style>
