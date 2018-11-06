<template>
<div>
    <div class="bot-box">
        <p>{{bot.name}}</p>
        <p>{{bot.attack}}</p>
        <p>{{bot.health}}</p>
        <button>Select</button>
        <button>Clear</button>
    </div>

</div>
</template>

<script>
export default {
    props: ['bot']
}
</script>

<style>
.bot-box {
    border: 1px solid #333;
    padding: 20px;
    width: 150px;
    text-align: center;
    margin-bottom: 20px;
}
</style>

