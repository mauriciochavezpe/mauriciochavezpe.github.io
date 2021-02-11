<template>
  <div id="about" class="container mx-auto">
    <div class="my-10">
      <h2 class="text-3xl my-4">About me</h2>
      <p
        class="text-left p-5 break-words"
        style="font-family: 'Times New Roman', sans-serif; font-size: 1.667rem"
      >
        Actualmente vivo en Lima, tengo 22 años, trabajo como consultor
        relacionada al ecosistema de la nube de SAP o (SCP), he desarrollado
        soluciones con multiples herramientas, aplicaciones web, chatbots y
        automatización de procesos con RPA.
        <br />
        Actualmente me encuentro estudiante las tecnologias de vueJS y Java.
      </p>
      <button v-on:click="openTabCV"
        class="border-blue-900 p-5 bg-blue-300 text-white bold-700 rounded-full hover:bg-blue-400 focus:outline-none focus:bg-blue-500"
      >
        Descargar CV
      </button>
    </div>
  </div>
</template>

<script>
// import Skill from "./Skill.vue";

export default {
  components: {
    // Skill,
  },
  data() {
    return {
      // stacks: [
      //   {
      //     name: "LENGUAGES",
      //     tecnologias: [
      //       { name: "JS", porcentaje: "80%" },
      //       { name: "HTML5", porcentaje: "80%" },
      //       { name: "Java", porcentaje: "40%" },
      //     ],
      //   },
      //    {
      //     name: "FRAMEWORKS",
      //     tecnologias: [
      //       { name: "SAPUI5", porcentaje: "80%" },
      //       { name: "nodejs", porcentaje: "70%" },
      //       { name: "express", porcentaje: "70%" },
      //       { name: "vueJS", porcentaje: "40%" },
      //     ],
      //   },
      //    {
      //     name: "OTHERS TOOLS",
      //     tecnologias: [
      //       { name: "API REST", porcentaje: "80%" },
      //       { name: "CHATBOT", porcentaje: "80%" },
      //       { name: "SAP CAI", porcentaje: "80%" },
      //       { name: "DIALOGFLOW", porcentaje: "70%" },
      //       { name: "CSS3", porcentaje: "70%" }, 
      //       { name: "GIT", porcentaje: "60%" },
      //       { name: "iRPA", porcentaje: "50%" },
      //       { name: "SQL", porcentaje: "50%" },
      //       { name: "UIPATH", porcentaje: "50%" },
      //       { name: "HANADB", porcentaje: "40%" },
      //     ],
      //   },
      // ],
    };
  },
  methods:{
    openTabCV:function () {
      window.open("https://drive.google.com/file/d/1Re3sPQBz6AxvKb-B4lxsdOeq4vfcrj-D/view","_blank")
    }
  }
};
</script>