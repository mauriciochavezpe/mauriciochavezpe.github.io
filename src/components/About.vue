<template>
  <div id="about" class="container mx-auto">
    <div class="my-10">
      <h2 class="text-3xl my-4">Más sobre mí</h2>
      <p
        class="text-center lg:text-left p-5 break-words"
        style="font-family: 'Times New Roman', sans-serif; font-size: 1.667rem"
      >
        Entusiasta con el mundo de la tecnologia, desarrollador JS, comprometido
        con lo que hago. Actuamente trabajo en consultoria logrando así
        desarrollar multiples soluciones empresariales.
        <br />
        Me gusta testear nuevas tecnologias, de momento estoy estudiando vuejs y
        python 😎
      </p>
      <button
        v-on:click="openTabCV"
        class="border-blue-900 p-5 bg-blue-300 text-white bold-700 rounded-full hover:bg-blue-400 focus:outline-none focus:bg-blue-500"
      >
        Descargar CV
      </button>
    </div>
  </div>
</template>

<script>
export default {
  components: {
    // Skill,
  },
  methods: {
    openTabCV: function() {
      window.open(
        "https://drive.google.com/file/d/1Re3sPQBz6AxvKb-B4lxsdOeq4vfcrj-D/view",
        "_blank"
      );
    },
  },
};
</script>
