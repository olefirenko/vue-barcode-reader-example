<script setup>
import { ref } from "vue";
import { StreamBarcodeReader } from "vue-barcode-reader";

const decodedText = ref("");

const onLoaded = () => {
  console.log("loaded");
};

const onDecode = (text) => {
  decodedText.value = text;
};
</script>

<template>
  <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
  <h2>The decoded value in QR/barcode is</h2>
  <h2>{{ decodedText }}</h2>

  <p class="information">
    <strong>Github:</strong>
    <a href="https://github.com/olefirenko/vue-barcode-reader" target="_blank"> https://github.com/olefirenko/vue-barcode-reader</a>
  </p>
  <p>
    <strong>NPM:</strong>
    <a href="https://www.npmjs.com/package/vue-barcode-reader" target="_blank"> https://www.npmjs.com/package/vue-barcode-reader</a>
  </p>
  <p>
    Check <strong>vue-barcode-reader</strong> library in production at
    <a href="https://parceltrackingapp.com/en" target="_blank">ParcelTrackingApp.com</a>
  </p>
</template>

<style scoped>
a {
  color: #42b983;
}
.information {
  margin-top: 100px;
}
</style>
