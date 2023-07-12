<template>
  <div class="card-stats">
    <div v-for="(stat, index) in infoArr" :key="index" class="one-third">
      <div class="stat-value">{{ stat.value }}</div>
      <div class="stat">{{ stat.title }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    infoArr: {
      type: Array
      //required: true
    }
  }
};
</script>

<style lang="scss">
</style>