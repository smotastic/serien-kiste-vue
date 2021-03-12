<template>
  <div>
    <div class="row">
      <watch v-for="item in list" :key="item.name" :movie="item" />
    </div>
    <q-btn round icon="add" @click="addMovie" />
  </div>
</template>

<script lang="ts">
import { Movie } from './models';
import { defineComponent, ref, Ref } from 'vue';
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
      description:
        'Ein unglaublich guter Film mit fliegenden Kindern, Ein unglaublich guter Film mit fliegenden Kindern, Ein unglaublich guter Film mit fliegenden Kindern, Ein unglaublich guter Film mit fliegenden Kindern',
    },
  ];
  const list: Ref<Movie[]> = ref(arr1);

  function addMovie() {
    list.value.push({ name: 'test', description: 'Hallo', director: 'Test' });
  }

  return { list, addMovie };
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
