<template>
  <app-layout title="Dashboard">
    <template #header>
      <h2 class="h4 font-weight-bold">
       <img style="width:25px" src="https://www.svgrepo.com/show/7027/chat.svg" alt=""> Chat room
      </h2>
    </template>

    <getData />

  </app-layout>
</template>
<style>
.addUnderBorder {
   border-bottom: 2px solid blueviolet;
}
</style>
<script>
import { defineComponent } from "vue"
import AppLayout from "@/Layouts/AppLayout.vue"
import getData from "@/Layouts/GetData.vue"

export default defineComponent({
  components: {
    AppLayout,
    getData
  },
  mounted() {
      $('.chatRoom').addClass('addUnderBorder');
  }
});
</script>
