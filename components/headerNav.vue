<template>
  <nav class="headerNav">
    <ul class="headerNav__menu">
      <li><nuxt-link to="/about">ABOUT</nuxt-link></li>
      <li><nuxt-link to="/news">NEWS</nuxt-link></li>
      <li><nuxt-link to="/contact">CONTACT</nuxt-link></li>
    </ul>
  </nav>
</template>
<script>
export default {
  components: {}
}
</script>

<style lang="scss" scoped>

.headerNav{
  position: absolute;
  right: 0;
  top: 0;
  width: 100%;
  height:100vh;
  padding-top: 5%;
  background-color: rgba(#000,.7);
  pointer-events: none;
  overflow: hidden;
  opacity: 0;
  z-index: 10;
  transition: .5s;
  &__menu{
    width: 100%;
    max-width: 600px;
    margin: 2em auto;
    li{
      margin: 2em 0;
      a{
        display: flex;
        align-items: center;
        width: 100%;
        height: 4em;
        color: #fff;
        padding-left: 1em;
      }
    }
  }
}
.headerMenu__btn.open + .headerNav{
  pointer-events: auto;
  opacity: 1;
}

</style>
