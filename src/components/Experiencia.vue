<template>
  <div class="container mx-auto">
    <div class="grid grid-cols-1 xl:grid-cols-3 gap-2">
      <div class="xl:row-span-3">
        <div class="w-full">
          <h2 class="text-center font-bold my-3">Experiencia</h2>
        </div>
      </div>
      <div class="w-full col-span-2 ">
        <ExperienciaEmpresa
          v-for="(emp, i) in empresas"
          v-bind:key="i"
          v-bind:empresa="emp"
        />
      </div>

      <div class="my-2 col-span-2">
        <div class="w-full p-5 text-left">
          <span id="resumen" v-on:click="irVerCV" class="text-3xl font-sans"
            >ver resumen</span
          >
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ExperienciaEmpresa from "./Experiencia-empresa.vue";
// import ExperienciaEmpresa from "./Experiencia-empresa.vue";
export default {
  components: { ExperienciaEmpresa },
  
  data() {
    return {
      empresas: [
        {
          nombre: "CSTI",
          cargo: "Consultor SCP",
          duracion: "Jul 2019 - Ene 2021",
        },
        {
          nombre: "INTELECTA",
          cargo: "Consultor SCP",
          duracion: "Ene 2019 - Jul 2019",
        },
        {
          nombre: "SISTEMASUNI",
          cargo: "Trainer dev",
          duracion: "Ago 2019 - Ene 2019",
        },
      ],
    };
  },
  methods: {
    irVerCV: function () {
      window.open(
        "https://drive.google.com/file/d/1Re3sPQBz6AxvKb-B4lxsdOeq4vfcrj-D/view",
        "_blank"
      );
    },
  },
  created: function () {},
};
</script>

<style  scoped>
#resumen:hover {
  cursor: pointer;
  color: royalblue;
  transition: all 0.3s ease-in-out;
}
#resumen:hover {
  transform: translateX(7px);
}
#resumen::after {
  content: "";
  background-size: 100%;
  background-image: url("../assets/resources/right-arrow.svg");
  width: 2.5rem;
  height: 2.5rem;
  vertical-align: middle;
  display: inline-block;
  margin-left: 1rem;
}
</style>