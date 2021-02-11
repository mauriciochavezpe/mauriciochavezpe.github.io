
<template>
  <div class="w-full h-96 bg-gray-200">
    <div
      id="menu"
      class="fixed z-20 h-screen transform -translate-x-full 
      duration-500 ease-in-out w-screen h-screen bg-red-200"    >
      <div
        class="w-full h-full flex flex-col justify-center align-center uppercase font-medium"
      >
        <a href="#about" class="text-3xl m-5">Acerca de </a>
        <a href="#servicios" class="text-3xl m-5">Servicios</a>
        <a href="#contacto" class="text-3xl m-5">Contacto</a>
        <a href="#" class="text-3xl m-5">Blog</a>
      </div>
    </div>

    <div class="h-full">
      <div id="box-btn" class="fixed right-5 mt-5 z-50">
        <button v-on:click="abrir_menu" class="mx-auto">
          <svg
            class="block h-6 w-6"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
      </div>
      <!--  -->
      <div class="w-full fixed z-10">
        <div
          id="navbar"
          class="duration-500 ease-in-out w-full flex justify-between items-center p-5 "
        >
          <div class="text-left xl:w-4/12">
            <span class="text-3xl">MCHAVEZ.PE</span>
          </div>
          
          <!-- menu option desktop  -->
          <div id="box-menu-opciones" class="flex justify-end">
            <a href="#about" class="text-lg mx-5">Acerca de </a>
            <a href="#servicios" class="text-lg mx-5">Servicios</a>
            <a href="#contacto" class="text-lg mx-5">Contacto</a>
            <a href="#" class="text-lg mx-5">Blog</a>
          </div>
        </div>
      </div>

      <div class="absolute w-full">
        <div
          class="mt-24 grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-2 z-0"
        >
          <div class="xl:col-span-2 flex justify-center">
            <img
              class="w-11/12 h-28 xl:w-full xl:h-3/5"
              src="../assets/resources/js.svg"
              alt=""
            />
          </div>
          <div class="w-full h-full flex justify-center">
            <div
              class="xl:mt-6 m-2 flex justify-center md:items-center xl:items-start"
            >
              <!-- <div class=""> -->
              <h2 class="md:text-4xl text-2xl xl:text-5xl" id="info_owner" />
              <!-- </div> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: "Header",
  data() {
    return {
      info_owner: "Hola soy Mauricio, \nFront-end developer.",
    };
  },
  methods: {
    maquina_escribir: function () {
      let i = 0;
      let descp_owner = this.info_owner;
      let chartInfo = descp_owner.split("");
      let that = this;

      if (document.getElementById("info_owner") !== null) {
        document.getElementById("info_owner").innerText = "";
      }

      let writeDescFor = setInterval(
        function () {
          let nodo = document.getElementById("info_owner");
          if (chartInfo[i] === " ") {
            nodo.innerText += " "; //chartInfo[i];
            nodo.innerText += ` ${chartInfo[i + 1]}`;
            i += 2;
          } else {
            nodo.innerText += `${chartInfo[i]}`;
            i++;
          }
          if (i === chartInfo.length) {
            clearInterval(writeDescFor);
            let writeDescForRever = setInterval(
              function () {
                chartInfo = descp_owner.slice(0, i);
                nodo.innerText = chartInfo;
                if (i == 0) {
                  clearInterval(writeDescForRever);
                  that.maquina_init();
                }
                i--;
              }.bind(this),
              250
            );
          }
        }.bind(this),
        250
      );
    },
    abrir_menu: function (oEvent) {
      if (
        document.getElementById("menu").classList.contains("-translate-x-full")
      ) {
        document.getElementById("menu").classList.remove("-translate-x-full");
        document.getElementById("menu").classList.remove("translate-x-full");
      } else {
        document.getElementById("menu").classList.remove("translate-x-full");
        document.getElementById("menu").classList.add("-translate-x-full");
      }
      console.log("x");
    },
    maquina_init: function () {
      this.maquina_escribir();
    },
  },
  created: function () {
    this.maquina_init();
    window.onscroll = function (oEvent) {
      
      let navbar = document.getElementById("navbar");
      let positionScroll = window.scrollY;
      
      if (positionScroll > 50) {
        navbar.classList.add("bg-gray-300");
      } else {
        navbar.classList.remove("bg-gray-300");
      }
    };
  },
};
</script>
<style scoped>
#info_owner {
  z-index: 0;
}
#info_owner::after {
  content: "|";
  color: "";
  animation: blink 0.5s infinite;
  animation-timing-function: ease;
  animation-direction: normal;
  animation-name: blink;
  z-index: 0;
  position: relative;
}
@keyframes blink {
  0% {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
#box-menu-opciones {
  display: none;
}

@media (min-width: 600px) {
  #box-menu-opciones {
    display: block;
  }
  #box-btn {
    display: none;
  }
}
</style>