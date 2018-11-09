<template>
<div>
        <div class="bot-box">
        <p>Name: {{bot.name}}</p>
        <p>Attack Level: {{bot.attack}}</p>
        <p>Health Level: {{bot.health}}</p>
        <button @click='selectBot(bot.name)'>Select</button>
        <button>Clear</button>
    </div>

</div>
</template>

<script>

export default {
    props: ['bot', 'i', 'select', 'botchoice'],
     data() {
        return {
            // bot1: '',
            // bot2: ''
        }
    
},
methods: {
    selectBot(bot) {
        this.botchoice(this.select.push(this.bot.name))
        console.log(this.select)
        }
    }
}

</script>

<style>
.bot-box {
    border: 1px solid #2c3e50;
    padding: 20px;
    width: 150px;
    text-align: center;
    margin: auto;
    margin-bottom: 20px;
}
button {
    padding: 10px;
    margin: 10px;
}
</style>

