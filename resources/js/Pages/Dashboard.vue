<template>
  <app-layout title="Dashboard">
    <template #header>
      <h2 class="h4 font-weight-bold">
        Dashboard
      </h2>
    </template>

    <welcome />
    <div class="container bg-dark">abc</div>
  </app-layout>
</template>
<style>
.addUnderBorder {
   border-bottom: 2px solid blueviolet;
   font-weight: bold;
}
</style>
<script>
import { defineComponent } from "vue"
import AppLayout from "@/Layouts/AppLayout.vue"
import Welcome from "@/Jetstream/Welcome.vue"

export default defineComponent({
  components: {
    AppLayout,
    Welcome
  },
  mounted() {
      $('.dashboard').addClass('addUnderBorder');
  }
});
</script>
