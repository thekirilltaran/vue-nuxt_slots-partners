<template>
  <li>
    <strong> {{item.title}}</strong>
    {{item.price}}
  </li>
</template>

<script>
export default {
  name: "ItemAdvan",
  props: {
    item: Object
  }
}
</script>

<style scoped lang="scss">
li {
  position: relative;
  padding-left: 70px;
  display: block;
  min-height: 45px;
  text-align: left;
  font-size: 14px;
  strong {
    display: block;
    font-weight: 700;
    font-size: inherit;
    margin-bottom: 5px;
  }
  &:not(&:last-child) {
    margin-bottom: 25px;
  }
  &:before,
  &:after {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    width: 45px;
    height: 45px;
    border-radius: 100%;
    overflow: hidden;
  }
  &:after {
    background: #fff3;
    background-image: url("static/img/icons/check.svg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: 15px 15px;
    filter: brightness(9);
  }
}
</style>
