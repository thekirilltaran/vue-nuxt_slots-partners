<template>
  <section class="section-advan">
    <div class="wrap">
      <Title>
        <h2>Тим, хто нагоняє Траф</h2>
      </Title>
      <ListsAdvan/>
    </div>
  </section>
</template>

<script>
import ListsAdvan from "./listsAdvan/ListsAdvan";
export default {
  name: "SectionAdvan.vue",
  components: {ListsAdvan}
}
</script>

<style scoped lang="scss">
@import "static/stylesScss/variable.scss";

.section-advan {
  padding: 123px 0 124px;
  @media (max-width: $table) {
    padding: 85px 0;
  }
  @media (max-width: $mob) {
    order: 1;
    padding: 50px 0 0;
  }
}

</style>
