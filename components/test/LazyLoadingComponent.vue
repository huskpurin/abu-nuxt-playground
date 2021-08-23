<template>
  <div>
    <h2>my lazy load comp</h2>
    <loading v-if="!isVisible" />
    <my-comp v-if="isVisible" />
  </div>
</template>
<script>
import LoadingComp from '@/components/test/Loading.vue';

export default {
  components: {
    loading: LoadingComp,
    'my-comp': () => import('@/components/test/MinorComponent.vue')
  },
  data: function () {
    return {
      isVisible: false
    };
  },
  mounted: function () {
    const observer = new IntersectionObserver((entries) => {
      if (entries[0].intersectionRatio <= 0) return;

      observer.unobserve(this.$el);
      this.isVisible = true;
    });
    observer.observe(this.$el);
  }
};
</script>
