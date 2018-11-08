<template>
    <div class="create">
        <p>Name: <input v-model='botName' type="text" /> </p>
        <p>Attack Level: <input v-model='attack' type="text" /></p>
        <p>Health Level: <input v-model='health' type="text" /></p>
        <button @click='createBot'>Add Bot</button>
        <button @click='clearInputs'>Clear</button>
    </div>
</template>

<script>
export default {
    name: 'create',
    props: ['add'],
    data() {
        return {
            botName: '',
            attack: '',
            health: ''
        }
    },
    methods: {
        clearInputs() {
            this.botName = '',
            this.attack = '',
            this.health = ''
        },
        createBot() {
            this.add(this.botName, this.attack, this.health)
        }
    }
}
</script>

<style>

</style>
