<template>
  <div class="close" @click.prevent="click">
    <svg class="icon">
      <use xlink:href="#close" href="img/sprite.svg#close"></use>
    </svg>
  </div>
</template>

<script>
export default {
  name: "BtnClose",
  methods: {
    click() {
      this.$emit('eventClick', this.target);
    }
  }

}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.close{
  position: absolute;
  top: 10px;
  right: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 40px;
  background: $grey6;
  cursor: pointer;
  z-index: 5;
  .icon {
    width: 14px;
    height: 14px;
  }
}
</style>
