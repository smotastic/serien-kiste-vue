<template>
  <div class="row">
    <watch v-for="item in list" :key="item.name" :movie="item" />
  </div>
</template>

<script lang="ts">
import { Movie } from './models';
import { defineComponent, ref } from 'vue';
import Watch from './Watch.vue';

function watchList() {
  let arr1: Movie[] = [
    {
      name: 'Hallo',
      director: 'Hans Wurst',
      description: 'Hallo du lieber Film',
    },
    {
      name: 'Watch me',
      director: 'Peter Pan',
      description: 'Ein unglaublich guter Film mit fliegenden Kindern',
    },
    {
      name: 'Noch einer',
      director: 'Markus',
      description: 'Ein unglaublich guter Film mit fliegenden Kindern',
    },
    {
      name: 'Geiler Film',
      director: 'Markus',
      description: 'Ein unglaublich guter Film mit fliegenden Kindern',
    },
  ];
  // eslint-disable-next-line @typescript-eslint/no-unsafe-assignment
  const list = ref(arr1);

  return { list };
}

export default defineComponent({
  name: 'WatchList',
  components: {
    Watch,
  },
  setup() {
    return { ...watchList() };
  },
});
</script>
