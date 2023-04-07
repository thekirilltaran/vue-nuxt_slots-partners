<template>
  <span class="icon-view">
    <svg class="icon">
      <use :xlink:href="xlinkHref" :href="href"></use>
    </svg>
  </span>
</template>

<script>
export default {
  name: "IconView.vue",
  props: {
    icon: String
  },
  computed: {
    href () {
      return `/img/sprite.svg#${this.icon}`;
    },
    xlinkHref () {
      return `#${this.icon}.svg`;
    }
  }
}
// console.log(this.icon);
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.icon-view {
  width: 65px;
  height: 65px;
  background-color: $primary;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 15px;
  flex-shrink: 0;
  @media (max-width: $mob) {
    width: 45px;
    height: 45px;
  }

  .icon {
    width: 35px;
    height: 35px;
    @media (max-width: $mob) {
      width: 25px;
      height: 25px;
    }
  }

  &.green {
    background-color: $green;
  }

  &.orange {
    background-color: $orange;
  }
}
</style>
