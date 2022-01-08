<template>
	<div>
		<header>
			<h1>Site</h1>
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
  h1{
    margin: 0;
  }
}
</style>