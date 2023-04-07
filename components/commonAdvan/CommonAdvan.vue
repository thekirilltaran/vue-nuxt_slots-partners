<template>
  <ul class="common-adv">
    <template v-for="item in lists">
      <ItemAdvan :item='item' />
    </template>
  </ul>
</template>

<script>
import ItemAdvan from './ItemAdvan';
export default {
  name: "commonAdvan",
  components: {ItemAdvan},
  data() {
    return {
      lists: [
        {
          title: 'CPA',
          price: '$25 і вище',
        },
        {
          title: 'REVSHARE',
          price: 'Піднімай до 60%',
        },
        {
          title: 'Гібрід',
          price: 'Зробимо як скажеш',
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
  .common-adv {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 20px 0 30px;
  }
</style>
