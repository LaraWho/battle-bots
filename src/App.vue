<template>
  <div>
      <h1>BATTLE BOTS</h1>

      <h2 @click='toggleCreate'>Create a Bot</h2>
      <h2 @click='toggleList'>See all Bots</h2>
      
      <section v-if='showCreate'>
        <Create :add='addBot'/>
      </section>

      <section v-if='showList' >
        <botlist v-for='(bot, i) in botList' :key='i' :bot='bot' :i='i' :select='selectBot'/>
      </section>

  </div>
</template>

<script>
import Botlist from './components/Botlist';
import Create from './components/Create';

export default {
  data() {
    return {
      botList: [{name: 'RuPaul', attack: '100', health: '100'}, {name: 'Violet', attack: '80', health: '90'}],
      selectedBots: [],
      showCreate: true,
      showList: false
    }
  },
  methods: {
    addBot(name, attack, health) {
      this.botList.push({
        name: name,
        attack: attack,
        health: health
    })
    this.toggleList()
    },
    toggleList() {
      this.showCreate = false;
      this.showList = true;
    },
    toggleCreate() {
      this.showCreate = true;
      this.showList = false;
    },
    selectBot() {
      console.log('select')
    }
  },
  components: {
    Create: Create,
    Botlist: Botlist
  }
}

</script>

<style>
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h2 {
  cursor: pointer;
}
</style>
