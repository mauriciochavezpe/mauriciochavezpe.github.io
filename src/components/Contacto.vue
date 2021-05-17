<template>
  <div class="container mx-auto my-2">
    <div class="w-full flex justify-between items-center">
      <div class=" w-full lg:w-1/2 h-auto p-5">
        <form class="grid grid-cols-2 gap-4" @submit="sendmail">
          <div class="w-full">
            <input
              type="text"
              id="names"
              class="w-full border p-2 rounded"
              placeholder="Nombres"
              v-model="$v.nombres.$model"
              autocomplete="off"
            />
            <div v-if="$v.nombres.$error">
                <span class="form__error" v-if="!$v.nombres.required">
                  El nombre es requerido.
                </span>
                <span class="form__error" v-if="!$v.nombres.minLength">
                  El Username debe tener a lo menos
                  {{ $v.nombres.$params.minLength.min }} caraceteres.
                </span>
              </div>
          </div>

          <div class="w-full">
            <input
              type="text"
              id="telef"
              class="w-full border p-2 rounded"
              placeholder="Apellidos"
              v-model="$v.apellido.$model"
              autocomplete="off"
            />
            <div v-if="$v.nombres.$error">
                <span class="form__error" v-if="!$v.apellido.required">
                  El apellido es requerido.
                </span>
                <span class="form__error" v-if="!$v.apellido.minLength">
                  El apellido debe tener a lo menos
                  {{ $v.apellido.$params.minLength.min }} caraceteres.
                </span>
              </div> 
            <!-- <div v-if="$v.telef.$error">
                <span class="form__error" v-if="!$v.telef.required">
                  telef es requerido.
                </span>
                <span class="form__error" v-if="!$v.telef.minLength">
                  El telef debe tener a lo menos
                  {{ $v.telef.$params.maxLength.max  }} caraceteres.
                </span>
              </div> -->
          </div>
          <div class="w-full col-span-2">
            <input
              type="text"
              id="email"
              class="w-full border p-2 rounded"
              placeholder="correo"
              v-model="$v.email.$model"
              autocomplete="off"
            />
             <div v-if="$v.email.$error">
                <span class="form__error" v-if="!$v.email.required">
                  Email Requerido.
                </span>
                <span class="form__error" v-if="!$v.email.email">
                  Ingrese un correo electrónico válido.
                </span>
              </div>
          </div>
          <div class="w-full   col-span-2">
            <input
              type="text"
              id="asunto"
              class="w-full border p-2   rounded"
              placeholder="asunto"
              v-model="$v.asunto.$model"
              autocomplete="off"
            />
             <div v-if="$v.asunto.$error">
                <span class="form__error" v-if="!$v.asunto.required">
                  El asunto es requerido.
                </span>
                <span class="form__error" v-if="!$v.asunto.minLength">
                  El Username debe tener a lo menos
                  {{ $v.asunto.$params.maxLength.max }} caraceteres.
                </span>
              </div>
          </div>
          <div class="w-full  col-span-2">
            <textarea
              type="text"
              rows="4"
              id="mensaje"
              class="w-full border p-2 rounded resize-none"
              placeholder="mensaje"
              v-model="$v.mensaje.$model" autocomplete="off"
            />
              <div v-if="$v.mensaje.$error">
                <span class="form__error" v-if="!$v.mensaje.required">
                  El mensaje es requerido.
                </span>
                <span class="form__error" v-if="!$v.mensaje.minLength">
                  El mensaje debe tener a lo menos
                  {{ $v.mensaje.$params.maxLength.max }} caraceteres.
                </span>
              </div>
            
          </div>
          <div class="w-full  col-span-2">
            <input
              type="submit"
              class="w-full border p-2 bg-green-600 rounded text-white"
              value="Enviar"
              
            />
              <!-- :disabled="$v.$invalid" -->
            
          </div>
        </form>
      </div>
      <div class="w-0 lg:w-1/2 ">
        <img class="w-full h-80" src="../assets/resources/team-chat.svg" />
      </div>
    </div>
  </div>
</template>

<script>
import { required, email, minLength,maxLength } from "vuelidate/lib/validators";
import axios from "axios";
export default {
  data() {
    return {
      nombres: "",
      apellido: "",
      telef: "",
      email: "",
      asunto: "",
      mensaje: "",
      isActive: false,
    };
  },
  validations: {
    nombres: { required, minLength: minLength(4) },
    apellido: { required, minLength: minLength(4) },
    email: { required, email },
    telef:{required, maxLength:maxLength(9)},
    asunto:{required, maxLength:maxLength(30)},
    mensaje:{required, maxLength:maxLength(10)},
  },
  // computed:{
  //   telef: function(){
  //     console.log("Ass");
  //   return this.telef;
  //   }
  // },
  methods: {
    sendmail: function(oEvent) {
      oEvent.preventDefault();
      axios.post("https://rest-mail-portafolio.herokuapp.com/api/mail",{
                "nombre":`${this.nombres}`,
                "correo":`${this.email}`,
                "mensaje":`asunto: ${this.asunto} - mensaje: ${this.mensaje} - telf: ${this.telef}`
            }).then(result=>console.log(result.data))
              .catch(e=>console.log(e))
    },
    created(){
      // console.log($v);
    }
  },
};
</script>

<style></style>
