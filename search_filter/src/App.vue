<template>
  <div>
    <!-- Called SearchFilter Components -->
    <SearchFilter />
  </div>
</template>

<script>

import SearchFilter from './components/SearchFilter.vue';

export default {
name: 'App',
  components: {
    SearchFilter
  },
};
</script>