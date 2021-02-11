<template>
  <footer class="bg-gray-200">
    <div class="container mx-auto">
      <div class="flex flex-col p-5">
        <div class="w-2/3 xl:w-1/3 mx-auto py-5">
          <p style="color: #000000" class="text-sm">
            Si llegaste hasta aquí, ya conoces parte de mí, a lo que me dedico,
            si gustas trabajar conmigo, contactame para comunicarnos.
          </p>
        </div>
        <!-- <div> -->
          <div class="flex justify-center xl:justify-start grid grid-cols-1 xl:grid-cols-2">
            <div class="flex justify-center xl:justify-start  items-center">
              <p style="color: #000000">
                © {{ actual }} - Web desarrollada por
                <a class="owner" href="#">Mauricio Chávez</a>
              </p>
            </div>
            <div class="w-full flex justify-center xl:justify-end">
              <div class="m-5">
                <a target="_blank" href="https://github.com/mauriciochavezpe"
                  ><img class="w-4" src="../assets/resources/github.svg"
                /></a>
              </div>
              <div class="m-5">
                <a
                  target="_blank"
                  href="https://www.linkedin.com/in/mauricio-chavez-pelayo-28b0ab133/"
                  ><img class="w-4" src="../assets/resources/linkedin.svg"
                /></a>
              </div>
              <div class="m-5">
                <a target="_blank" href="tel:+51944606812"
                  ><img class="w-4" src="../assets/resources/smartphone.svg"
                /></a>
              </div>
               <div class="m-5">
                <a target="_blank" href="mailto:ed.chavez.pe@gmail.com"
                  ><img class="w-4" src="../assets/resources/mail.svg"
                /></a>
              </div>
            </div>
          </div>
        </div>
      <!-- </div> -->
    </div>
  </footer>
</template>
<script>
export default {
  name: "Footer",
  data() {
    return {
      actual: new Date().getFullYear(),
    };
  },
};
</script>
