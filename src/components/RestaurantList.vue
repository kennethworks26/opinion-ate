<template>
  <div>
    <div>RestaurantList</div>
    <ul>
      <li
        v-for="restaurant in restaurants"
        :key="restaurant.id"
        data-testid="restaurant"
      >
        {{ restaurant.name }}
      </li>
    </ul>
  </div>
</template>

<script>
import {mapActions, mapGetters} from 'vuex';

export default {
  name: 'RestaurantList',
  computed: {
    ...mapGetters({
      restaurants: 'restaurants/records',
    }),
  },
  methods: {
    ...mapActions({
      loadRestaurants: 'restaurants/load',
    }),
  },
  mounted() {
    this.loadRestaurants();
  },
};
</script>
