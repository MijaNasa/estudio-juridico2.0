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
        <p>&copy; 2024 Estudio Jurídico Laboral. Todos los derechos reservados.</p>
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

// 🔷 Hero adaptado a derecho laboral
const heroData = ref({
  title: "Defendemos al trabajador",
  subtitle: "Respondemos SIN CARGO todas tus consultas",
  backgroundImage: "/placeholder.svg?height=600&width=1200" // Reemplazá por imagen laboral si querés
})

// 📞 Datos de contacto
const contactData = ref({
  whatsappNumber: "5493417799783", // Número de WhatsApp actualizado
  whatsappMessage: "Hola, quiero consultar por un problema laboral"
})

// 🔍 Sección informativa sobre derecho laboral
const infoData = ref({
  title: "Abogado especializado en Derecho Laboral",
  description: "Nuestro estudio jurídico se dedica exclusivamente a la defensa de trabajadores. Ya sea que hayas sido despedido, no estés registrado o sufras acoso laboral, te ayudamos a reclamar lo que te corresponde.",
  services: [
    "Despidos con y sin causa",
    "Trabajo no registrado (en negro)",
    "Indemnizaciones y diferencias salariales",
    "Acoso laboral y mobbing",
    "Accidentes de trabajo y reclamos a ART",
    "Liquidación final y recibos mal liquidados"
  ],
  image: "/placeholder.svg?height=400&width=600" // Reemplazar por imagen de temática laboral
})

// 🧾 Testimonios laborales
const testimonialsData = ref([
  {
    name: "Juan Pérez",
    text: "Me despidieron sin motivo y gracias al abogado recuperé todo lo que me correspondía. Excelente atención.",
    rating: 5
  },
  {
    name: "Laura Gómez",
    text: "Trabajé en negro por años y me ayudaron a hacer el reclamo completo. Totalmente recomendable.",
    rating: 5
  },
  {
    name: "Martín Sosa",
    text: "Tuve un accidente en el trabajo y la ART no respondía. El estudio me acompañó en todo el proceso.",
    rating: 5
  }
])

// 📣 CTA final
const ctaData = ref({
  title: "Reclamá lo que te corresponde como trabajador",
  subtitle: "Tu consulta es confidencial y sin compromiso. Contactanos ahora por WhatsApp."
})
</script>

<style>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
</style>