<template>
  <div class="social-btn">
    <label for="soc-tel">
      <input checked id="soc-tel" type="radio" class="hidden" name="form-social">
      <span class="wrp">
                                                <svg class="icon">
                                                    <use xlink:href="#telegram" href="img/sprite.svg#telegram"></use>
                                                </svg>
                                            </span>
    </label>
    <label for="soc-skp">
      <input id="soc-skp" type="radio" class="hidden" name="form-social">
      <span class="wrp">
                                                <svg class="icon">
                                                    <use xlink:href="#skype" href="img/sprite.svg#skype"></use>
                                                </svg>
                                            </span>
    </label>
  </div>
</template>

<script>
export default {
  name: "Social"
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.social-btn {
  display: flex;
  align-items: center;
  margin: 0 -5px;
  label {
    margin: 0 5px;
    cursor: pointer;
  }
  .wrp {
    padding: 10px;
    width: 45px;
    height: 45px;
    border-radius: 100%;
    display: block;
    transition: background-color .3s;
  }
  .icon {
    width: 25px;
    height: 25px;
  }
  input:checked + .wrp {
    background: $grey6;
  }
}
</style>
