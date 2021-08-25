<template>
  <div>
    <h1>This is a minor component</h1>
    <img src="https://cdn2.thecatapi.com/images/1r1.jpg" />
  </div>
</template>
<script>
console.log('js loaded');

import BitmovinApi from '@bitmovin/api-sdk';

const bitmovinApi = new BitmovinApi({apiKey: '<YOUR_API_KEY>'});

export default {
  created() {
    console.log('created');
  },
  mounted() {
    console.log('mounted', bitmovinApi);
  }
}
</script>
