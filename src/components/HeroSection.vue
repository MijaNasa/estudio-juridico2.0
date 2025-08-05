<template>
  <section class="relative min-h-screen flex items-center justify-center text-white overflow-hidden pt-16">
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 z-0">
      <img 
        :src="backgroundImage" 
        :alt="'Fondo de estudio jurídico'"
        class="w-full h-full object-cover"
      />
      <div class="absolute inset-0 bg-slate-900/80"></div>
    </div>
    
    <!-- Content -->
    <div class="relative z-10 w-full px-4 sm:px-6 lg:px-8 text-center">
      <div class="max-w-6xl mx-auto">
        <h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight">
          {{ title }}
        </h1>
        <p class="text-xl md:text-2xl lg:text-3xl mb-8 text-slate-200 max-w-4xl mx-auto">
          {{ subtitle }}
        </p>
        
        <ContactButton 
          :whatsappNumber="whatsappNumber"
          :whatsappMessage="whatsappMessage"
          size="large"
          class="inline-flex"
        />
        
        <!-- Trust indicators con mejor espaciado -->
        <div class="mt-16 grid grid-cols-1 md:grid-cols-3 gap-8 max-w-4xl mx-auto text-slate-300">
          <div class="flex items-center justify-center gap-3">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            <span class="text-base font-medium">+15 años de experiencia</span>
          </div>
          <div class="flex items-center justify-center gap-3">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            <span class="text-base font-medium">Consulta gratuita</span>
          </div>
          <div class="flex items-center justify-center gap-3">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            <span class="text-base font-medium">Atención personalizada</span>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </div>
  </section>
</template>

<script setup>
import ContactButton from './ContactButton.vue'

defineProps({
  title: {
    type: String,
    required: true
  },
  subtitle: {
    type: String,
    required: true
  },
  backgroundImage: {
    type: String,
    required: true
  },
  whatsappNumber: {
    type: String,
    required: true
  },
  whatsappMessage: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
@keyframes bounce {
  0%, 20%, 53%, 80%, 100% {
    transform: translateY(0);
  }
  40%, 43% {
    transform: translateY(-30px);
  }
  70% {
    transform: translateY(-15px);
  }
  90% {
    transform: translateY(-4px);
  }
}

.animate-bounce {
  animation: bounce 1s infinite;
}
</style>
