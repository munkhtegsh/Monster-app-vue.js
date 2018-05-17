<template>
  <div id="app">
    <h1> MONSTER SMASH </h1> 
    <button @click='toggleCreate(false)'>CREATE</button>   
    <button @click='toggleCreate(true)'>MONSTERS</button> 
    
     <create v-if='!showCreate' :getMonster='saveMonsters'>
     </create>

     <monsters v-else :monsters="this.monsters" >
     </monsters>
  </div>
</template>
<script>
import Create from './components/Create';
import Monsters from './components/Monsters';

export default {
  name: 'app',
    data () {
    return {
      showCreate: '',
      showMonsters: '',
      monsters: []
    }
  },
  methods: {
    toggleCreate(bool) {
      this.showCreate = bool;
    },
    saveMonsters(monsters) {
      this.monsters.push(monsters)
    }
  },
  components: {
    create: Create,
    monsters: Monsters
  },
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
