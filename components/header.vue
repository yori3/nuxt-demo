<template>
	<div>
		<header>
			<div class="siteName">Site</div>
      <div class="headerMenu">
			<HeaderNav />
      </div>
		</header>
	</div>
</template>
<script>
	import HeaderNav from "@/components/headerNav.vue";
	export default {
		components: {
			HeaderNav
		}
	};
</script>

<style lang="scss" scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5em 4%;
  .siteName{
    font-size: 2em;
  }
}
</style>