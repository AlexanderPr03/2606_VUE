<template>
  <!-- <ListItemComponent></ListItemComponent> -->
   <div class="container">

    <ListItemComponent v-for="produs of produse" :key="produs.id" @counterUpdatedPlus="incrementCounter" @counterUpdatedMinus="decrementCounter"
    :titluProdus="produs.titluProdus" :pretProdus="produs.pretProdus" />

    <!-- <ListItemComponent @counterUpdatedPlus="incrementCounter" @counterUpdatedMinus="decrementCounter" v-bind:titluProdus="titluTask1" /> -->
   </div>
   
   <h1>{{ counter }}</h1>
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
      titluTask1: 'Samsung Galaxy M34 128 GB Silver',
      counter:0,
      produse: [
        {
          id:0,
          titluProdus:'Samsung Galaxy M34 128 GB Silver',
          pretProdus:'4 199',
        },
        {
          id:1,
          titluProdus:'Laptop Apple MacBook Pro 14 2023 Space Gray',
          pretProdus:'35 990 ',
        },
        {
          id:2,
          titluProdus:'Smart Tracker Apple AirTag MX542RU/A White',
          pretProdus:'2 399',
        },
        {
          id:3,
          titluProdus:'Carte electronică Kindle Scribe 2022 with Premium Pen Tungsten 32 GB Black',
          pretProdus:'11 499',
        }
      ]
    }
  },
  methods: {
      incrementCounter() {
        this.counter++;
      },
      decrementCounter() {
        this.counter--;
      }
  }

  // $emit - emitem datele/evenimentele în sus
  // props - emitem datele în jos
  
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
.container {
  display: flex;
  justify-content:space-around;
  margin-bottom: 200px;
  flex-wrap: wrap;
  gap: 20px;
}
</style>

<!-- 
<script>

ListItemComponent.addEventListener('counterUpdatedPlus', incrementCounter);


form.addEventListener('submit', function(event) {
  event.preventDefault();
})
</script> -->