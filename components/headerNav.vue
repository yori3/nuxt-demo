<template>
  <div>
    <nav class="headerNav">
      <ul class="headerNav__menu">
        <li><nuxt-link to="/about">ABOUT</nuxt-link></li>
        <li><nuxt-link to="/news">NEWS</nuxt-link></li>
        <li><nuxt-link to="/contact">CONTACT</nuxt-link></li>
      </ul>
    </nav>
  </div>
</template>
<script>
	export default {
		components: {}
	};
</script>

<style lang="scss" scoped>

.headerNav{
  &__menu{
    display: flex;
    li{
      margin-right: 1.5em;
    }
  }
}

</style>