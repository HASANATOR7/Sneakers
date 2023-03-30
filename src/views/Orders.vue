<template>
  <section class="order">
    <div class="container">
      <div class="order__top">
        <router-link to="/">
          <svg
            width="35"
            height="35"
            viewBox="0 0 35 35"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect
              x="0.5"
              y="0.5"
              width="34"
              height="34"
              rx="7.5"
              fill="white"
              stroke="#F2F2F2"
            />
            <path
              d="M19 22L14 17L19 12"
              stroke="#C8C8C8"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </router-link>
        <h1 class="order__title">Мои заказы</h1>
      </div>
      <div class="order__content">
        <div class="order_empty"></div>
        <Card v-for="good in goods" :key="good.id" :good="good" />
      </div>
    </div>
  </section>
</template>

<script>
import Card from "../components/Card.vue";
import { useStore } from "vuex";
export default {
  components: { Card },
  setup() {
    const store = useStore();
    const goods = store.state.orders;


    


    return {
        goods,

    };
  },
};
</script>


<style lang="scss">
.order {
  &__top {
    display: flex;
    padding-top: 42px;
  }
  &__title {
    font-weight: 700;
    font-size: 32px;
    color: #000000;
    margin-left: 21px;
  }

  &__content {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
  }
}
</style>