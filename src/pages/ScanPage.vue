<template>
  <div>
    <qrcode-stream @detect="onDetect"></qrcode-stream>
  </div>
</template>

<script setup>
import { QrcodeStream, QrcodeDropZone, QrcodeCapture } from "vue-qrcode-reader";

function onDetect(a) {
  console.log(a);
}
</script>