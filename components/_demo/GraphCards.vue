<template>
  <div class="flex flex-row flex-wrap flex-grow mt-2">
    <Graph1 />
    <Graph2 />
  </div>
</template>

<script>
import Graph1 from '~/components/_demo/Graph1.vue';
import Graph2 from '~/components/_demo/Graph2.vue';

export default {
  components: {
    Graph1,
    Graph2
  }
};
</script>
