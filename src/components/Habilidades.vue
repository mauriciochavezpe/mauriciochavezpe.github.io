<template>
  <div class="container mx-auto skill-soft">
    <div class="mx-10 my-5">
      <h2 class="text-3xl">Algunas tecnologias</h2>
    </div>
    <div class="mt-5">
      <!-- <div class="grid grid-cols-1 xl:grid-cols-3 gap-2"> -->
      <!-- <Skill
            class="px-5"
            v-for="(stack, i) in stacks"
            v-bind:key="i"
            v-bind:stack="stack"
          /> -->
      <div class="mx-6 my-2">
        <div class="grid grid-cols-3 md:grid-cols-5 gap-2">
          <Skill v-for="(too,i) in tecnologias" v-bind:key="i" v-bind:tool="too"/>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Skill from "./Skill.vue";
import html5 from "@/assets/resources/tech/html5.svg";
import vuejs from "@/assets/resources/tech/vuejs.svg";
import js from "@/assets/resources/tech/js.svg";
import nodejs from "@/assets/resources/tech/nodejs.svg";
import uipath from "@/assets/resources/tech/uipath.svg";
import git from "@/assets/resources/tech/git.svg";
import postgresql from "@/assets/resources/tech/postgresql.svg";
import java from "@/assets/resources/tech/java.svg";
import dialogflow from "@/assets/resources/tech/dialogflow.svg";

export default {
  components: {
    Skill,
  },
  data() {
    return {
      tecnologias: [
        { name: "HTML5", url: html5 },
        { name: "Java", url: java },
        { name: "nodejs", url: nodejs },
        { name: "vueJS", url: vuejs },
        { name: "DialogFlow", url: dialogflow },
        { name: "SQL", url: postgresql },
        { name: "GIT", url: git },
        { name: "JS", url: js },
        { name: "UIPATH", url: uipath }
      ],
    };
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
<style scope></style>
