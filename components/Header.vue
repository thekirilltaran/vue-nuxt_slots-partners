<template>
  <header class="header">
    <div class="wrap">

      <div class="block">
        <a href="" class="logo">
          <img src="img/logo.svg" alt="logo">
        </a>
      </div>

      <div class="action">
        <Button class="transparent fixed" @eventClick="showModal" target="DesignPart">Show input state</Button>
        <Button class="transparent" @eventClick="showModal" target="modal-signIn">Вхід</Button>
        <Button @eventClick="showModal" target="modal-signUp">Реєстрація</Button>
      </div>

      <Modal @eventClick="closeModal" :modalOpened="modalOpened" :modalAction="modalAction"/>
    </div>
  </header>
</template>

<script>
  export default {
    name: "SectionAdvan.vue",
    data() {
      return {
        modalOpened: false,
        modalAction: ''
      }
    },
    methods: {
      showModal(target) {
        this.modalOpened = true;
        this.modalAction = target;
        document.body.classList.add('no-scroll');
      },
      closeModal() {
        this.modalOpened = false;
        this.modalAction = '';
        document.body.classList.remove('no-scroll');
      }
    },
  }
</script>


<style lang="scss" scoped>
@import "static/stylesScss/variable.scss";
.header {
  border-bottom: 1px solid $grey7;
  padding: 24px 0;
  position: relative;
  @media (max-width: $mob) {
    padding: 10px 0;
  }
  .logo {
    display: inline-block;
    margin-right: 10px;
    @media (min-width: 1025px) {
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
    }
    img {
      max-width: 100%;
    }
  }
  .btn {
    margin-left: 15px;
    @media (max-width: $table) {
      margin-left: 10px;
    }
  }
  .wrap {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    max-width: 1420px;
    @media (max-width: $table) {
      justify-content: space-between;
    }
  }
  .action {
    display: flex;
    align-items: center;
  }
}

</style>
