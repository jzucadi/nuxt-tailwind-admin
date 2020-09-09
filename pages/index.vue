<template>
  <BaseContainer>
    <MetricCards />
    <GraphCards />
    <Table />
  </BaseContainer>
</template>

<script>
import BaseContainer from '~/components/containers/BaseContainer.vue';
import MetricCards from '~/components/_demo/MetricCards.vue';
import GraphCards from '~/components/_demo/GraphCards.vue';
import Table from '~/components/_demo/Table.vue';

export default {
  components: {
    BaseContainer,
    MetricCards,
    GraphCards,
    Table
  }
};
</script>
