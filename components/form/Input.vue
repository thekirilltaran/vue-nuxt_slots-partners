<template>
  <div class="field">
    <template v-if="label">
      <label class="label">{{label}}</label>
    </template>
    <div class="input">
      <input :type="type" :placeholder="placeholder" :value="value">
      <template  v-if="inputType === 'password' && name !== 'error'">
        <div class="icon-info btn-pass">
          <svg class="icon">
            <use xlink:href="#eye" href="img/sprite.svg#eye"></use>
          </svg>
        </div>
      </template>
      <template  v-if="name === 'error'">
        <div class="icon-info hide-pass">
          <svg class="icon">
            <use xlink:href="#close" href="img/sprite.svg#close"></use>
          </svg>
        </div>
      </template>
    </div>
    <template v-if="name === 'error'">
      <div class="message-form">Display error message here.</div>
    </template>
  </div>
</template>

<script>
  export default {
    name: "Input.vue",
    props: {
      type: String,
      placeholder: String,
      label: String,
      value: String,
      name: String,
      inputType: String
    },
  }
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.field {
  position: relative;
  z-index: 10;
  .icon-info {
    position: absolute;
    right: 18px;
    top: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 20px;
    height: 20px;
    border-radius: 20px;
    cursor: pointer;
    z-index: 5;
    &.btn-pass,
    &.hide-pass {
      cursor: pointer;
    }
    &.btn-pass {
      .icon {
        width: 24px;
        height: 24px;
      }
    }
    &.hide-pass {
      background: #353945;
    }

    &.btn-close {
      background: $grey6;

      .icon {
        width: 8px;
        height: 8px;
      }
    }

    .icon {
      width: 12px;
      height: 12px;
    }
  }

  &:hover {
    input {
      border-color: $grey5;
    }
  }

  .message-form {
    padding: 5px 16px;
    display: block;
    font-size: 10px;
    font-weight: 400;
    line-height: 12px;
    letter-spacing: 0em;
    text-align: left;
  }

  .label {
    font-family: $rb;
    font-size: 12px;
    font-weight: 700;
    line-height: 12px;
    letter-spacing: 0em;
    text-align: left;
    text-transform: uppercase;
    display: block;
    margin: 20px 0 12px;
  }

  &.error {
    input {
      border-color: $orange;
      color: $orange;
    }

    .message-form {
      color: $orange;
    }
  }

  &.success {
    .input {
      &:after {
        content: '';
        position: absolute;
        right: 18px;
        top: 50%;
        transform: translateY(-50%);
        display: flex;
        align-items: center;
        justify-content: center;
        width: 20px;
        height: 20px;
        border-radius: 20px;
        cursor: pointer;
        z-index: 5;
        background-image: url("static/img/icons/check.svg");
        background-repeat: no-repeat;
        background-position: center;
        background-size: 12px 8px;
      }
    }

    input {
      border-color: $green;
    }
  }

  &.click {
    input {
      border-color: $primary;
    }
  }

  &:not(&:last-child) {
    margin-bottom: 10px;
  }

  .input, .textarea {
    position: relative;
  }

  input, textarea {
    width: 100%;
    padding: 15px;
    border-radius: 25px;
    border: 2px solid $grey6;
    background-color: $grey7;
    color: #fff;
    font-size: 14px;
    font-weight: 700;
    text-align: left;
    transition: border-color .3s;
  }

  input {
    height: 48px;
  }

  textarea {
    min-height: 120px;
    max-height: 150px;
    resize: vertical;
  }

  ::-webkit-input-placeholder { /* WebKit, Blink, Edge */
    color: #777E90;
  }

  :-moz-placeholder { /* Mozilla Firefox 4 to 18 */
    color: #777E90;
    opacity: 1;
  }

  ::-moz-placeholder { /* Mozilla Firefox 19+ */
    color: #777E90;
    opacity: 1;
  }

  :-ms-input-placeholder { /* Internet Explorer 10-11 */
    color: #777E90;
  }

  ::-ms-input-placeholder { /* Microsoft Edge */
    color: #777E90;
  }

  ::placeholder { /* Most modern browsers support this now. */
    color: #777E90;
  }
}

</style>
