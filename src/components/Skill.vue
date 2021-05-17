<template>
  <!-- <div> -->
    <div class="w-full border rounded-md shadow-lg p-2 flex flex-col  justify-center">
      <div class="flex justify-center items-end ">
        <img class="w-1/2 h-min-full lg:w-8 lg:h-8" v-bind:src="tool.url" />
      </div>
      <p class="p-2 text-base wrapping">
        {{tool.name}}
      </p>
    </div>
    <!-- <div>
          <h3 class="text-center my-3">{{stack.name}}</h3>
        </div> -->
    <!-- <div class="tool flex justify-between w-full" v-for="(s,i) in stack.tecnologias" :key="i"> -->
    <!-- <div class="text-left  w-1/3">
          <h4>{{s.name}}</h4>
        </div> -->
    <!-- <div class="flex w-2/3">
          <div class="w-full">
            <div class="shadow w-full bg-gray-100 rounded-md h-3"> -->
    <!-- <div
                class="bg-blue-500 text-xs leading-none py-1 h-full text-center text-white"
                v-bind:style="{width:s.porcentaje}"
              > -->
    <!-- {{s.porcentaje}} -->
    <!-- </div> -->
    <!-- </div>
          </div>
        </div> -->
    <!-- </div> -->
  <!-- </div> -->
</template>
<script>
export default {
  name: "Skill",
  props: ["tool"],
};
</script>
