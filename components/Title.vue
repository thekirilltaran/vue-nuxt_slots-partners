<template>
  <div class="title">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Title.vue"
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.title {
  margin-bottom: 25px;
  display: flex;
  align-items: center;
  justify-content: center;

  h1 {
    font-size: 40px;
    @media (max-width: $mob) {
      font-size: 25px;
    }
  }

  h2,h3,h4,h5,h6 {
    font-size: 32px;
  }
  h1,h2,h3,h4,h5,h6 {
    font-family: $gl;
    font-weight: 700;
    line-height: 48px;
    letter-spacing: 0em;
    text-align: center;
    color: $grey2;
    @media (max-width: $mob) {
      font-size: 25px;
      line-height: normal;
    }
  }

}
</style>
