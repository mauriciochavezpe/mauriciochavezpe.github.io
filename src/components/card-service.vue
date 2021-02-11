<template>
     <div class="w-full my-2 rounded ">
        <div class="mx-6  flex flex-col justify-center h-full bg-gray-100 items-center  p-5">
        <img class="w-2/5" :src="servicio.img"/>
        <div class="flex my-3 justify-center align-center w-full">
          <p class="text-base font-medium">{{servicio.nombre}}</p>
        </div>
        </div>
      </div>

</template>

<script>
export default {
    props:["servicio"]
    
}
</script>