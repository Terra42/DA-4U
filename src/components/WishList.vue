<template>
  <div class="wish_list">
    <wish
      class="wish"
      v-for="(wish, index) in wishes"
      v-bind:wish="wish"
      v-bind:key="index"
      v-bind:wishlistID="wishlistID"
      v-bind:userType="userType"
    />
  </div>
</template>
<script>
import Wish from "./Wish.vue";

export default {
  name: "WishList",

  components: {
    wish: Wish,
  },

  props: ["wishes", "wishlistID", "userType"],
};
</script>
<style scoped>
.wish_list {
  display: flex;
  flex-direction: column;
  width: 90vw;
}

@media (min-width: 640px) {
  .wish_list {
    flex-direction: row;
    flex-wrap: wrap;
  }
  .wish {
    flex: 0 0 45%;
  }
}

@media (min-width: 1280px) {
  .wish {
    flex: 0 0 32%;
  }
}
</style>
