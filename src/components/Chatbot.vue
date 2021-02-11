<template>
  <!-- transition-all duration-300 ease-in-out hidden xl:block w-16 h-16 fixed xl:overflow-hidden -->
  <div
    id="chatbot"
  >
    <div
      id="icono"
      class="h-full w-full overflow-hidden after:bg-no-repeat"
    ></div>

    <iframe
      id="ventana_chat"
      allow="microphone;"
      src="https://console.dialogflow.com/api-client/demo/embedded/3dfc08c1-5314-4014-bb63-6916b97ce46d"
    ></iframe>
  </div>
</template>

<script>
export default {
  methods: {
    close_chat: function () {
      document.getElementById("icono").classList.remove("hidden");
      document.getElementById("icono").classList.add("block");
      btnChat.classList.remove("h--34");
      btnChat.classList.remove("w--32");

      document.getElementById("ventana_chat").classList.remove("w-full");
      document.getElementById("ventana_chat").classList.remove("h-full");
    },
  },
  created: function () {
    // let btnChat;
    let btnChat = document.getElementById("chatbot");
    btnChat.addEventListener("click", function () {
      if (btnChat.classList.contains("h--34")) {
        btnChat.classList.remove("h--34");
        btnChat.classList.remove("w--32");
        document.getElementById("icono").classList.add("block");
        document.getElementById("ventana_chat").classList.remove("w-full");
        document.getElementById("ventana_chat").classList.remove("h-full");
      } else {
        document.getElementById("icono").classList.add("hidden");
        document.getElementById("icono").classList.remove("block");
        btnChat.classList.add("h--34");
        btnChat.classList.add("w--32");
        document.getElementById("ventana_chat").classList.add("w-full");
        document.getElementById("ventana_chat").classList.add("h-full");
      }
    });
    let oEvents = ["keydown"];
    oEvents.map(event => {
      window.addEventListener(event, function (oEvent) {
        if (event == "keydown") {
          if (oEvent.key == "Escape") {
            this.close_chat();
          }
        }
        else {
          if (btnChat.classList.contains("h--34")) {
            this.close_chat();
          }
        }
      })
    })
  },
};
</script>
<style scoped>
#icono::after {
  content: "";
  background-image: url("../assets/resources/charla.svg");
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  display: block;
}

.h--34 {
  height: 430px !important;
}

.w--32 {
  width: 350px !important;
}
</style>