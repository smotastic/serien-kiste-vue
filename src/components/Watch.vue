<template>
  <div class="col q-pa-md">
    <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">{{ movie.name }}</div>
        <div class="text-subtitle2">Von {{ movie.director }}</div>
      </q-card-section>
      <q-separator inset />
      <q-card-section> {{ movie.description }} </q-card-section>
    </q-card>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { Movie } from './models';

export default defineComponent({
  name: 'Watch',
  props: {
    movie: {
      type: Object as PropType<Movie>,
      required: true,
    },
  },
  setup() {
    return {};
  },
});
</script>
