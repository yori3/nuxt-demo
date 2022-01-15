<template>
  <div>
    <header>
      <div class="header__inner">
        <div class="siteName">
          Site
        </div>
      </div>
      <button class="headerMenu__btn" v-bind:class="{open:isOpen}" @click="isOpen=!isOpen">
        <span></span>
      </button>
      <HeaderNav />
    </header>
  </div>
</template>

<script>
import HeaderNav from '@/components/headerNav.vue'
export default {
  components: {
    HeaderNav
  },
  data: () => ({
    isOpen: false
  })
}

</script>

<style lang="scss" scoped>
header{
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 5000;
  .header__inner{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 60px;
    padding: 0 4%;
    background-color: #fff;
  }
  .siteName{
    font-size: 2em;
  }
}

.headerMenu__btn{
  position: absolute;
  right: 0;
  top: 0;
  width: 60px;
  height: 60px;
  background-color: #61a6c6;
  z-index: 100;
  span{
    position: absolute;
    left: 50%;
    top: 50%;
    width: 24px;
    height: 3px;
    border-radius: 30px;
    background-color: #fff;
    transform: translate(-50%, -50%);
    transition: background .8s;
    &::before, &::after {
      display: block;
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: inherit;
      border-radius: inherit;
      background-color: #fff;
      content: "";
    }
    &::before {
      transform: rotate(0) translateY(-300%);
      animation-name: barToggleTopReverse;
      animation-duration: .8s;
      animation-direction: reverse;
    }
    &::after {
      transform: rotate(0) translateY(300%);
      animation-name: barToggleBottomReverse;
      animation-duration: .8s;
      animation-direction: reverse;
    }
  }
  &.open{
    span{
      background-color: transparent;
      &::before{
        top: 0;
        transform: rotate(-45deg);
        animation-name: barToggleTop;
        animation-duration: .8s;
        animation-direction: normal;
      }
      &::after{
        bottom: 0;
        transform: rotate(45deg);
        animation-name: barToggleBottom;
        animation-duration: .8s;
        animation-direction: normal;
      }
    }
  }
}

@keyframes barToggleTop {
  0% {
    transform: rotate(0) translateY(-300%);
  }
  50% {
    top: 0;
    transform: rotate(0) translateY(0);
  }
  100% {
    top: 0;
    transform: rotate(-45deg) translateY(0);
  }
}

@keyframes barToggleBottom {
  0% {
    transform: rotate(0) translateY(300%);
  }
  50% {
    bottom: 0;
    transform: rotate(0) translateY(0);
  }
  100% {
    bottom: 0;
    transform: rotate(45deg) translateY(0);
  }
}

@keyframes barToggleTopReverse {
  0% {
    transform: rotate(0) translateY(-300%);
  }
  50% {
    top: 0;
    transform: rotate(0) translateY(0);
  }
  100% {
    top: 0;
    transform: rotate(-45deg) translateY(0);
  }
}

@keyframes barToggleBottomReverse {
  0% {
    transform: rotate(0) translateY(300%);
  }
  50% {
    bottom: 0;
    transform: rotate(0) translateY(0);
  }
  100% {
    bottom: 0;
    transform: rotate(45deg) translateY(0);
  }
}
</style>
