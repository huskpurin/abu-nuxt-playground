<template>
  <div>
    <loading v-if="!isVisible" />
    <bitmovin v-if="false" />
  </div>
</template>
<script>
import Loading from '@/components/test/Loading.vue';
// import MyComp from '@/components/test/MinorComponent.vue';

export default {
  components: {
    loading: Loading,
    'bitmovin': () => import('@/components/test/MinorComponent.vue')
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
