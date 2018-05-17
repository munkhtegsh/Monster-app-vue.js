<template>
  <div div="monsters">
    <p>Winner is: {{ winner }}</p>
    <button @click='getWinner()'> BATTLE </button>
    <monster 
      v-for='(monster, i) in monsters' 
      :key='i'
      :monster='monster'
      >
    </monster>
  </div>
</template>

<script>
import Monster from './Monster';
export default {
  name: 'monsters',
  data () {
    return {
      winner: ''
    }
  },
  props: ['monsters'],
  methods: {
    getWinner() {
      console.log(this.monsters)
      let winner = Math.floor(Math.random() * (this.monsters.length));
      this.winner = this.monsters[winner].name; 
    }
  },
  components: {
    monster: Monster
  },
}
</script>

<style>
</style> 