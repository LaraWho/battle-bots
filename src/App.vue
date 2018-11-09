<template>
  <div>
      <h1>BATTLE BOTS</h1>

      <h2 @click='toggleCreate'>Create a Bot</h2>
      <h2 @click='toggleList'>See all Bots</h2>
      

      <section v-if='showCreate'>
        <Create :add='addBot'/>
      </section>

      <section v-if='showList' >
        <p>Battle Bot #1 is ... {{selectedBots[0]}}</p>
        <p>Battle Bot #2 is ... {{selectedBots[1]}}</p>
        <botlist v-for='(bot, i) in botList' :key='i' :bot='bot' :i='i' :select='selectedBots' :botchoice="select"/>
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
    select(bots) {
      //  this.selectedBots.push({
      //    bot1: bot1,
      //    bot2: bot2
      //  })
      console.log('selectBot method in app.vue', this.selectedBots, bots)
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
