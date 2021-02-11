<template>
     <div class="container mx-auto skill-soft">
      <div class="mx-10 my-5">
        <h2 class="text-5xl">Skills</h2>
      </div>
      <div class="mt-5">
        <div class="grid grid-cols-1 xl:grid-cols-3 gap-2">
          <Skill
            class="px-5"
            v-for="(stack, i) in stacks"
            v-bind:key="i"
            v-bind:stack="stack"
          />
        </div>
      </div>
    </div>
</template>
<script>
import Skill from "./Skill.vue";

export default {
  components: {
    Skill,
  },
  data() {
    return {
      stacks: [
        {
          name: "LENGUAGES",
          tecnologias: [
            { name: "JS", porcentaje: "80%" },
            { name: "HTML5", porcentaje: "80%" },
            { name: "Java", porcentaje: "40%" },
          ],
        },
         {
          name: "FRAMEWORKS",
          tecnologias: [
            { name: "SAPUI5", porcentaje: "80%" },
            { name: "nodejs", porcentaje: "70%" },
            { name: "express", porcentaje: "70%" },
            { name: "vueJS", porcentaje: "40%" },
          ],
        },
         {
          name: "OTHERS TOOLS",
          tecnologias: [
            { name: "API REST", porcentaje: "80%" },
            { name: "CHATBOT", porcentaje: "80%" },
            { name: "SAP CAI", porcentaje: "80%" },
            { name: "DIALOGFLOW", porcentaje: "70%" },
            { name: "CSS3", porcentaje: "70%" }, 
            { name: "GIT", porcentaje: "60%" },
            { name: "iRPA", porcentaje: "50%" },
            { name: "SQL", porcentaje: "50%" },
            { name: "UIPATH", porcentaje: "50%" },
            { name: "HANADB", porcentaje: "40%" },
          ],
        },
      ],
    };
  },
  methods:{
    openTabCV:function () {
      window.open("https://drive.google.com/file/d/1Re3sPQBz6AxvKb-B4lxsdOeq4vfcrj-D/view","_blank")
    }
  }
};
</script>
<style scope>

</style>