<template>
<div>
    <p>{{i, bot.name}}</p>
    <div class="bot-box">
        <p>Name: {{bot.name}}</p>
        <p>Attack Level: {{bot.attack}}</p>
        <p>Health Level: {{bot.health}}</p>
        <button @click='selectBot'>Select</button>
        <button>Clear</button>
    </div>

</div>
</template>

<script>

export default {
    props: ['bot', 'i', 'select'],
     data() {
        return {
            selectedBots: []
        }
    
},
methods: {
    selectBot() {
        console.log('wat')
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

