<template>
      <div >
        <div>
          <h3 class="text-center my-3">{{stack.name}}</h3>
        </div>
      <div class="tool flex justify-between w-full" v-for="(s,i) in stack.tecnologias" :key="i">
        <div class="text-left  w-1/3">
          <h4>{{s.name}}</h4>
        </div>
        <div class="flex w-2/3">
          <div class="w-full">
            <div class="shadow w-full bg-gray-100 rounded-md">
              <div
                class="bg-blue-500 text-xs leading-none py-1 text-center text-white"
                v-bind:style="{width:s.porcentaje}"
              >
                {{s.porcentaje}}
              </div>
            </div>
          </div>
        </div>
      </div>
      </div>
</template>
<script>
export default {
    name:"Skill",
    props:["stack"]
}
</script>