<template>
  <div class="block-choice">
    <span class="title-block">Оберіть спосіб звязку</span>
    <div class="action-btn">
      <Social/>
      <Input type="text" placeholder="@телеграм_адреса"/>
    </div>
  </div>
</template>

<script>
import Social from '../Social';
import Input from '../form/Input';

export default {
  name: "SocialConnect",
  components: {Social, Input}
}
</script>

<style scoped lang="scss">
@import "static/stylesScss/variable.scss";

.block-choice {
  margin: 25px 0;
  .title-block {
    font-family: $rb;
    font-size: 12px;
    font-weight: 700;
    line-height: 12px;
    letter-spacing: 0em;
    text-align: center;
    display: block;
    margin-bottom: 10px;
    text-transform: uppercase;
  }
  .action-btn {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .field {
    margin-left: 10px;
    ::v-deep {
      input {
        text-align: center;
      }
    }
  }
}

</style>
