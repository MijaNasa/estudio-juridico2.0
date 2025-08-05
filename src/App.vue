<template>
  <div class="min-h-screen min-w-screen bg-white">
    <!-- Navbar -->
    <Navbar class="min-w-screen"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Hero Section -->
    <HeroSection 
      :title="heroData.title"
      :subtitle="heroData.subtitle"
      :backgroundImage="heroData.backgroundImage"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Info Section -->
    <InfoSection 
      :title="infoData.title"
      :description="infoData.description"
      :services="infoData.services"
      :image="infoData.image"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Testimonials Section -->
    <TestimonialsSection :testimonials="testimonialsData" />
    
    <!-- Final CTA Section -->
    <FinalCTASection 
      :title="ctaData.title"
      :subtitle="ctaData.subtitle"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Footer -->
    <footer class="bg-slate-900 text-white py-8">
      <div class="container mx-auto px-4 text-center">
        <p>&copy; 2024 Estudio Jurídico Especializado. Todos los derechos reservados.</p>
        <p class="text-slate-400 text-sm mt-2">Matrícula profesional: XXXXX</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import HeroSection from './components/HeroSection.vue'
import InfoSection from './components/InfoSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import FinalCTASection from './components/FinalCTASection.vue'
import Navbar from './components/Navbar.vue'

// Datos editables del Hero
const heroData = ref({
  title: "¿Estás pasando por un divorcio complicado?",
  subtitle: "Te ayudamos a proteger tus derechos y los de tu familia con asesoramiento legal especializado",
  backgroundImage: "/placeholder.svg?height=600&width=1200"
})

// Datos de contacto
const contactData = ref({
  whatsappNumber: "5491123456789", // Reemplazar por número real
  whatsappMessage: "Hola, quiero consultar sobre mi caso"
})

// Datos de la sección informativa
const infoData = ref({
  title: "¿Cómo trabajamos en tu caso?",
  description: "Nuestro estudio se especializa en derecho de familia, brindando asesoramiento integral y personalizado. Entendemos que cada situación es única y requiere un enfoque específico.",
  services: [
    "Divorcios consensuados y contenciosos",
    "Régimen de visitas y tenencia de menores",
    "Liquidación de sociedad conyugal",
    "Violencia familiar y medidas cautelares",
    "Adopciones y filiación",
    "Alimentos y cuota alimentaria"
  ],
  image: "/placeholder.svg?height=400&width=600"
})

// Datos de testimonios
const testimonialsData = ref([
  {
    name: "María González",
    text: "Excelente atención y profesionalismo. Me ayudaron en un momento muy difícil y lograron el mejor resultado para mi familia.",
    rating: 5
  },
  {
    name: "Carlos Rodríguez",
    text: "Muy recomendable. Transparentes en sus honorarios y siempre disponibles para resolver mis dudas.",
    rating: 5
  },
  {
    name: "Ana Martínez",
    text: "Gracias a su trabajo pude resolver mi situación de manera rápida y favorable. Totalmente profesionales.",
    rating: 5
  }
])

// Datos del CTA final
const ctaData = ref({
  title: "No esperes más para resolver tu situación legal",
  subtitle: "Contactanos ahora y recibí asesoramiento especializado sin compromiso"
})
</script>

<style>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
</style>