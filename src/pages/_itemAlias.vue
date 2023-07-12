<template>
  <div class="wrapper-person">
    <dir v-if="item">
      <img :src="item.img" :alt="item.descr" />
      <h1 style="color: #fff" class="title">{{ item.title }}</h1>
      <p>{{ item.descr }}</p>

      <CardStats :infoArr="item.info" />

      <div>
        <router-link to="/" class="btn btnPrimary">Back to home</router-link>
      </div>
    </dir>
  </div>
</template>

<script>
import items from '@/seeders/items.js';
import CardStats from '@/components/UI/CardStats';

export default {
  components: {
    CardStats
  },
  data() {
    return {
      item: null
    };
  },
  created() {
    const alias = this.$route.params.itemAlias;
    const item = items.find(el => el.alias === alias);

    // this.item = item

    item ? (this.item = item) : this.$router.push({ name: '404' });
  }
};
</script>

<style lang="scss">
.wrapper-person {
  text-align: center;
  .card-stats {
    margin: 30px 0;
    border-radius: 14px;
  }
}
</style>