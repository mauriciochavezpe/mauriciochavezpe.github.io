<template>
  <div class="home">
    
    <Header/>
     <About/>
    <Habilidades/>
   <Experiencia/>
    <Servicios/>
    <Portafolio/>
    <Contacto/>
    <Footer/> 
    <!-- <Chatbot/> -->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'
import About from '@/components/About.vue'
import Habilidades from '@/components/Habilidades.vue'
import Experiencia from '@/components/Experiencia.vue'
import Servicios from '@/components/Servicios.vue'
import Portafolio from '@/components/Portafolio.vue'
import Footer from '@/components/Footer.vue'
import Contacto from '@/components/Contacto.vue'
// import Chatbot from '@/components/Chatbot.vue'
export default {
  name: 'Home',
  components: {
    // HelloWorld,
    Header ,
    About,
    Experiencia,
    Habilidades,
    Servicios,
    Portafolio,
    Footer,
    Contacto
    // Chatbot
  }
}

</script>
