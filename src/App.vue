<template>
  <div>
      <h1>BATTLE BOTS</h1>

      <h2 @click='toggleCreate'>Create a Bot</h2>
      <h2 @click='toggleList' >See all Bots</h2>
      <section v-if='showCreate'>
        <Create :add='addBot'/>
      </section>

      <section v-if='showList' >
        <botlist v-for='(bot, i) in botList' :key='i' :bot='bot'/>
      </section>

  </div>
</template>

<script>
import Botlist from './components/Botlist';
import Create from './components/Create';

export default {
  data() {
    return {
      botList: [{name: 'test', attack: '100', health: '50'}],
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
    console.log(this.botList)
    this.toggleList()
    },
    toggleList() {
      this.showCreate = false;
      this.showList = true;
      console.log(this.showList)
    },
    toggleCreate() {
      this.showCreate = true;
      this.showList = false;
    }
  },
  components: {
    Create: Create,
    Botlist: Botlist
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
h2 {
  cursor: pointer;
}
</style>
