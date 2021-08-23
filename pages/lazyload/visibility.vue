<template>
  <div>
    <h1>visibility</h1>
    <!-- 3. by visibility -->
    <!-- https://markus.oberlehner.net/blog/lazy-load-vue-components-when-they-become-visible/ -->
    <!-- long text area + lazy load component -->
    <p v-for="n in 1" v-bind:key="n">
      {{ n }}
    </p>
    <my-lazy-load-comp />
  </div>
</template>
<script>
import MyLazyLoadComp from '@/components/test/LazyLoadingComponent.vue';

export default {
  components: {
    'my-lazy-load-comp': MyLazyLoadComp
  }
};
</script>
