<template>
  <div class="flex flex-wrap">
    <MetricCard
      icon="fa-wallet"
      icon-color="orange-600"
      title="New Tasks"
      value="15"
      arrow="up"
      arrow-color="blue-600"
    />
    <MetricCard
      icon="fa-users"
      icon-color="orange-600"
      title="Open Tasks"
      value="249"
      arrow="equal"
      arrow-color="blue-500"
    />
    <MetricCard
      icon="fa-user-plus"
      icon-color="orange-600"
      title="Recently Closed"
      value="2"
      arrow="up"
      arrow-color="blue-600"
    />

    <MetricCard
      icon="fa-server"
      icon-color="blue-600"
      title="Overdue"
      value="2"
    />
  </div>
</template>

<script>
import MetricCard from '~/components/widgets/MetricCard.vue';

export default {
  components: {
    MetricCard
  }
};
</script>

<style scoped></style>
