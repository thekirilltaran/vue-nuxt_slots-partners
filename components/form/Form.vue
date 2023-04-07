<template>
  <form action="/static" class="form">
    <slot></slot>
  </form>
</template>

<script>

export default {
  name: "Form",
}
</script>

<style scoped lang="scss">
.form {
  .btn {
    margin: 0 auto;
    width: fit-content;
  }
}
</style>
