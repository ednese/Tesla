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
    cursor: pointer;
}
@media screen and (max-width: 850px) {
    .footer > ul {
        margin: 0;
        top: 370px;
        flex-direction: column;
    }
    .footer > ul > li {
        text-align: center;
        max-width: 80%;
    }
}
</style>
