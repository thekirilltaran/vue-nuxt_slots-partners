<template>
  <div class="block">
    <slot name="title-modal"></slot>
    <Form>
      <Input type="mail" placeholder="Ваш email"/>
      <Input type="password" placeholder="Ваш пароль"/>
      <Button class="large">Війти</Button>
    </Form>
  </div>
</template>

<script>
import Form from './Form';
import Input from './Input';

export default {
  name: "SignIn",
  components: {Form,
    Input}
}
</script>

<style scoped lang="scss">

</style>
