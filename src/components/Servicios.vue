<template>
  <section id="servicios" class="container mx-auto">
    <div class="m-10">
      <h2 class="text-5xl">Servicios</h2>
    </div>
    <div class="grid grid-cols-1 xl:grid-cols-3">
        <card-service  v-for="(servicio,i) in servicios" :key="i" v-bind:servicio="servicio"/>
    </div>
  </section>
</template>
<script>
import img1 from "@/assets/resources/education.svg";
import img2 from "@/assets/resources/img2.svg";
import img3 from "@/assets/resources/img3.svg";
import cardService from "./card-service.vue";
export default {
  components: { cardService },
  data() {
    return {
      servicios: [
        { nombre: "Desarrollo Web", img: img1 },
        { nombre: "Desarrollo de Integraciones", img: img2 },
        { nombre: "Chatbots", img: img3 },
      ],
    };
  },
};
</script>

<style scoped>
:root {
}
.box:hover {
  /* background-color:#c3c3c3; */
}
</style>