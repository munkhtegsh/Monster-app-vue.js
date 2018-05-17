<template>
  <div id="create"> 
    <form action="" @submit.prevent='addMonsters'>
      <p>Name: {{name}}</p>   
      <input type="text" v-model='name' placeholder="Add name..."> 
      <p>Health: {{health}}</p>   
      <input type="text" v-model='health' placeholder="Add health..." > 
      <p>Attack: {{attack}}</p>   
      <input type="text" v-model='attack'  placeholder="Add attack..."> 
      <br/>
      <button @click="info(this.monsters)">CREATE</button>
    </form> 
  </div>
</template>

<script>
export default {
  name: 'create',
  data () {
    return {
      name: '',
      health: '',
      attack: '',
      monsters: []
    }
  },

  props: ['getMonster'],

  methods: {
   changeName() {
     name: this.name
   },
   addMonsters() {
     let newMonster = {
       name: this.name,
       health: this.health,
       attack: this.attack
     }
     this.getMonster(newMonster);
     this.name = '';
     this.health = '';
     this.attack = '';
   }
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
