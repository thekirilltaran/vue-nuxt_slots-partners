<template>
  <a href="" @click.prevent="click" class="btn">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "Button.vue",
  props: {
    target: String
  },
  methods: {
    click() {
      this.$emit('eventClick', this.target);
    }
  }
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.btn {
  border: 2px solid $primary;
  background-color: $primary;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: $gl;
  font-size: 14px;
  font-weight: 700;
  line-height: 16px;
  letter-spacing: 0em;
  padding: 10px 14px;
  border-radius: 90px;
  text-align: center;
  color: #141416;
  transition: opacity .3s, background .3s, border-color .3s, color .3s;
  &.fixed {
    position: fixed;
    right: 30px;
    bottom: 30px;
    z-index: 10;
  }
  &.large {
    font-size: 16px;
    padding: 14px 22px;
  }
  &.disabled {
    pointer-events: none;
    &:not(.transparent) {
      opacity: 0.5;
    }
    &.transparent {
      background: #FCFCFD;
      border-color: #FCFCFD;
      color: $grey7;
      opacity: 0.5;
    }
  }
  &.transparent {
    border-color: $grey5;
    color: #fff;
    background: $grey8;
    @media (min-width: 1025px) {
      &:hover {
        background: #FCFCFD;
        border-color: #FCFCFD;
        color: $grey7;
      }
    }
  }
  @media (min-width: 1025px) {
    &:not(.transparent) {
      &:hover {
        opacity: 0.75;
      }
    }
  }
}
</style>
