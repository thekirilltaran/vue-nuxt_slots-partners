<template>
  <div class="block">
    <slot name="title-modal"></slot>
    <Form>
      <Input label="Default"
             type="text"
             placeholder="Input caption"/>
      <Input label="Click on"
             type="text"
             placeholder="Input caption"
             class="click"
             value="Input caption"/>
      <Input label="Error"
             type="text"
             placeholder="Input caption"
             class="error"
             name="error"
             value="Input caption"/>
      <Input label="Hover"
             type="text"
             placeholder="Input caption"
             class="hover"/>
      <Input label="Input completed"
             type="text"
             placeholder="Input caption"
             class="completed"
             value="Input caption"/>
      <Input label="Success"
             type="text"
             placeholder="Input caption"
             class="success"
             value="Input caption"/>
      <Input label="Show password"
             type="text"
             placeholder="Ваш пароль"
             value="Input caption"
             inputType="password"/>
      <Input label="Password"
             type="password"
             placeholder="Ваш пароль"
             value="Input caption"
             inputType="password"/>
      <Button class="large">Війти</Button>
    </Form>
  </div>
</template>

<script>
import Form from "./Form";
import Input from "./Input";

export default {
  name: "ViewDesign",
  components: {Form,
    Input}
}
</script>

<style scoped>

</style>
