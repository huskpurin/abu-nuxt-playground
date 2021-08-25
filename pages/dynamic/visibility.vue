<template>
  <div>
    <h1>condition</h1>
    <p v-for="n in 100" v-bind:key="n">
      {{ n }}
    </p>
    <Intersect @enter="isVisible = true">
      <LazyDynamicBitmovinPlayer v-if="isVisible" />
      <DynamicLoading v-else />
    </Intersect>
  </div>
</template>
<script>
import Intersect from 'vue-intersect'

export default {
  components: { Intersect },
  data() {
    return {
      isVisible: false,
    }
  }
}
</script>
