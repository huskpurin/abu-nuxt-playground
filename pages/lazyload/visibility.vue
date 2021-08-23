<template>
  <div>
    <h1>visibility</h1>
    <!-- 3. by visibility -->
    <!-- https://markus.oberlehner.net/blog/lazy-load-vue-components-when-they-become-visible/ -->
    <!-- long text area + lazy load component -->
    <p v-for="n in 100" v-bind:key="n">
      {{ n }}
    </p>
    <lazy-load />
  </div>
</template>
<script>
import LazyLoadingComponent from '@/components/test/LazyLoadingComponent.vue';

export default {
  components: {
    'lazy-load': LazyLoadingComponent,
  }
};
</script>
