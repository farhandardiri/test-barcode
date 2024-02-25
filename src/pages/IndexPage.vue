<template>
  <q-page class="flex flex-center">

    <div
      class="row items-center"
      style="height: 100vh"
    >
      <q-btn
        color="primary"
        icon="camera_alt"
        label="Scan Barcode"
        size="lg"
        class="full-width"
        @click="iniciarLeitor()"
        v-show="cameraStatus === 0"
      />
    </div>
  </q-page>
</template>

<script setup>
import { Quagga } from "quagga";
import { ref } from "vue";

const dialog = ref(false);
const code = ref("");
const cameraStatus = ref(0);

function iniciarLeitor() {
  cameraStatus.value = 1;
  Quagga.init({
    inputStream: {
      nama: "Live",
      typeof: "LiveStream",
      target: document.querySelector("#scan"),
    },
  });
}
</script>
