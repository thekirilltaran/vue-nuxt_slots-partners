<template>
  <div class="title-modal">
    <IconView :class="iconClass" :icon="iconImg"/>
    <slot></slot>
  </div>
</template>

<script>
import IconView from "../IconView";
export default {
  name: "TitleModal",
  components: {IconView},
  props: {
    iconClass: String,
    iconImg: String
  }
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable';

.icon-view {
  width: 45px;
  height: 45px;
  ::v-deep {
    .icon {
      width: 25px;
      height: 25px;
    }
  }
}

.title-modal {
  font-family: $gl;
  font-size: 25px;
  font-weight: 700;
  line-height: 25px;
  letter-spacing: 0em;
  color: #fff;
  display: flex;
  align-items: center;
  margin-bottom: 25px;

  .icon-view {
    margin-right: 10px;
  }
}
</style>
