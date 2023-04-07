<template>
  <div class="item-advan">
    <IconView :icon="item.icon"/>
    <span class="title-block">{{item.title}}</span>
    <p>{{item.desc}}</p>
  </div>
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
@import 'static/stylesScss/variable.scss';

.item-advan {
  padding: 0 15px;
  width: calc(31.33% - 40px);
  text-align: center;
  margin: 0 20px;
  @media (max-width: $table) {
    padding: 0;
    width: calc(31.33% - 20px);
    margin: 0 10px;
  }
  @media (max-width: $mob) {
    width: calc(100% - 20px);
    position: relative;
    padding-left: 70px;
    &:not(&:last-child) {
      margin-bottom: 25px;
    }
  }
  .icon-view {
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 25px;
    @media (max-width: $mob) {
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
    }
  }
  .title-block {
    font-family: Roboto;
    font-size: 16px;
    font-weight: 500;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: center;
    color: $grey4;
    max-width: 250px;
    margin: 0 auto 25px;
    display: block;
    @media (max-width: $table) {
      margin-bottom: 10px;
    }
    @media (max-width: $mob) {
      text-align: left;
      margin: 0 0 5px;
    }
  }
  p {
    text-align: center;
    @media (max-width: $mob) {
      text-align: left;
    }
  }
}
</style>
