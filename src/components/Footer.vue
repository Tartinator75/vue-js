<template>
    <footer>
        <div class="header-element">element gauche</div>
        <div class="header-element">Copyright Ynov 2020</div>
        <div class="header-element">element droite</div>
    </footer>
</template>
<script>
    export default {
  name: 'Footer'
}
</script>
<style scoped lang="scss">
footer{
    height: 30px;
    display: flex;
    justify-content: space-between;
    background: #42b983;
}
</style>