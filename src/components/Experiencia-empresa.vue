<template>
  <div class="w-full">
    <div class="xl:text-left">
      <div class="flex justify-end items-center mx-6">
        <div class="font-sans text-left w-1/3">
          <div>
            <h2 class="text-sm xl:text-xl font-semibold">{{ empresa.nombre }}</h2>
          </div>
          <div>
            <span class="text-xs xl:text-sm text-right xl:text-left">{{ empresa.cargo }}</span>
          </div>
        </div>
        <div class="w-full w-2/3">
          <div class="w-full flex justify-end xl:justify-end">
            <span class=" font-incosolato text-sm xl:text-md ">{{ empresa.duracion }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Experiencia-empresa",
  props: ["empresa"],
};
</script>
<style   scoped>
.font-incosolato {
  font-family: "Inconsolata", monospace;
  /* font-size :0.rem; */
}
</style>