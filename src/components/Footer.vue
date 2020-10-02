<template>
    <div class="footer">
      <ul>
        <li>Tesla © 2020</li>
        <li>Mentions légales</li>
        <li>Contact</li>
        <li>Carrières</li>
        <li>Newsletter</li>
        <li>Actualités</li>
        <li>Localisations</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
.footer > ul {
    display: flex;
    position: relative;
    top: 370px;
}
.footer > ul > li {
    margin: 0 10px;
}
</style>
