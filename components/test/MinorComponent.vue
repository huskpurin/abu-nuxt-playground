<template>
  <div>
    <h1>This is a minor component</h1>
    <img src="https://cdn2.thecatapi.com/images/1r1.jpg" />
  </div>
</template>
<script>
import BitmovinApi from '@bitmovin/api-sdk';

const bitmovinApi = new BitmovinApi({apiKey: '<YOUR_API_KEY>'});

export default {
  mounted() {
    console.log(bitmovinApi);
  }
}
</script>
