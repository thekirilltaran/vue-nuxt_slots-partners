<template>
  <div class="rating">
    <svg class="icon">
      <use xlink:href="#megaphone" href="img/sprite.svg#star"></use>
    </svg>
    <svg class="icon">
      <use xlink:href="#megaphone" href="img/sprite.svg#star"></use>
    </svg>
    <svg class="icon">
      <use xlink:href="#megaphone" href="img/sprite.svg#star"></use>
    </svg>
    <svg class="icon">
      <use xlink:href="#megaphone" href="img/sprite.svg#star"></use>
    </svg>
    <svg class="icon">
      <use xlink:href="#megaphone" href="img/sprite.svg#star"></use>
    </svg>
  </div>
</template>

<script>
export default {
  name: "Rating.vue"
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.rating {
  display: flex;
  justify-content: center;
  .icon {
    width: 13px;
    height: 13px;
    margin: 0 13.5px;
    display: inline-block;
  }
}
</style>
