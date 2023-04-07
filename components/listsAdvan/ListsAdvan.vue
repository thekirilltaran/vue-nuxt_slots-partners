<template>
  <div class="list-advan">
    <template v-for="item in lists">
      <ItemAdvan :item='item' />
    </template>
  </div>
</template>

<script>
import ItemAdvan from "./ItemAdvan";
export default {
  name: "ListsAdvan",
  components: {ItemAdvan},
  data() {
    return {
      lists: [
        {
          icon: 'megaphone',
          title: 'Круті акції, призи та прибуткова бонусна програма',
          desc: 'Ми постійно працюємо над тим, щоб вам було цікаво та вигідно!',
        },
        {
          icon: 'smile',
          title: 'Особлива підтримка для кожного 24/7',
          desc: 'У вас буде свій персональний менеджер',
        },
        {
          icon: 'chart',
          title: 'Детальна статистика',
          desc: 'Миттєве оновлення, зрозуміла система відображення статистики',
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
@import 'static/stylesScss/variable.scss';

.list-advan {
  display: flex;
  flex-wrap: wrap;
  padding-top: 44px;
  width: calc(100% + 40px);
  margin-left: -20px;
  justify-content: space-between;
  flex-wrap: wrap;
  @media (max-width: $table) {
    width: calc(100% + 20px);
    margin-left: -10px;
    padding-top: 30px;
  }
  @media (max-width: $mob) {
    padding-top: 5px;
  }
}
</style>
