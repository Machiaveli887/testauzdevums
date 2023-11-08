<template>
    <footer>
        <p>DispoCars</p>
        <a href="tel:+3712999999" class="phone">+371 2999999</a>
        <a href="mailto:support@dispocars.com" class="email">support@dispocars.com</a>
    </footer>
</template>
<script>
 export default {
    name: 'AppFooter',
 }
</script>
<style>
    .phone {
        
        margin-left: 570px;
        margin-right: 70px;
        color: white;
    }

    .email {
        margin-right: 200px;
        color: white;
    }

    p {
        color: white;
        text-align: center;
    }
    
    footer {
        background-color: rgb(59, 28, 144);
    }
</style>