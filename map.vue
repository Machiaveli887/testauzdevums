<template>
<div class="root">
    <div>
        <p>Estamited arrival Time {{ time }}</p>
        <p>Driver statuss {{ status }}</p>
    </div>
    <img src="" alt="">
</div>
</template>
<script>
 export default {
    name: 'App-Map',
    data(){
        return{
            time: '11:15',
            status: 'SCHEDULED'
        }
    }
 }
</script>
<style scoped>
    .root{
        display: flex;
        flex-direction: column;
    }
</style>