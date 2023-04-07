<template>
  <div class="modal" :class="modalOpened ? 'open': ''">
<!--    modal-signUp-->
    <div
      class="modal-content"
      :class="{
        'openModal': modalOpened,
        'modal-signUp': modalAction === 'modal-signUp'
    }"
    >

      <BtnClose @eventClick="click"/>

      <template v-if="modalAction === 'DesignPart'">
        <ViewDesign>
          <template v-slot:title-modal>
            <TitleModal iconClass="green">You can see all states input form</TitleModal>
          </template>
        </ViewDesign>
      </template>

        <template v-if="modalAction === 'modal-signUp'">
          <SignUp>
            <template v-slot:title-modal>
              <TitleModal iconClass="green" iconImg="user">Реєстрація</TitleModal>
            </template>
          </SignUp>
        </template>

        <template v-if="modalAction === 'modal-signIn'">
          <SignIn>
            <template v-slot:title-modal>
              <TitleModal iconClass="orange" iconImg="lock">Вхід</TitleModal>
            </template>
          </SignIn>
        </template>
    </div>
  </div>
</template>

<script>
import BtnClose from "./BtnClose";
import TitleModal from "../modal/TitleModal";
import SignIn from "../form/SignIn";
import SignUp from "../form/SignUp";
import ViewDesign from '../form/ViewDesign'

export default {
  name: "Modal.vue",
  components: {BtnClose,
    SignIn,
    SignUp,
    TitleModal,
    ViewDesign
  },
  props: {
    modalOpened: Boolean,
    modalAction: String,
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

.modal{
  display: none;
  opacity: 0;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 100%;
  background: #353945e6;
  transition: .2s;
  z-index: 99;
  overflow-y: auto;
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;
  justify-content: center;
  padding: 0 10px;
  @media (min-height: 650px) and (min-width: 1025px) {
    align-items: center;
  }
  &.open{
    display: flex;
    opacity: 1;
    pointer-events: all;
  }

  .modal-content {
    opacity: 0;
    padding: 25px 30px 30px;
    position: relative;
    transition: .4s;
    z-index: 25;
    min-width: 290px;
    max-width: 355px;
    width: 100%;
    border-radius: 25px;
    overflow: hidden;
    background-color: $grey7;
    margin: 40px auto;
    height: fit-content;
    &.openModal{
      opacity: 1;
    }

    &.modal-signUp {
      max-width: 770px;
      padding: 0;
      @media (max-width: $table) {
        max-width: 350px;
      }
    }
  }
}


</style>
