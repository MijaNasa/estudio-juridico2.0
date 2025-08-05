<template>
  <section id="contacto" class="py-20 md:py-32 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900 text-white relative overflow-hidden">
    <!-- Background pattern -->
    <div class="absolute inset-0 opacity-10">
      <div class="absolute inset-0" style="background-image: radial-gradient(circle at 1px 1px, white 1px, transparent 0); background-size: 20px 20px;"></div>
    </div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Content -->
        <div class="text-center lg:text-left">
          <h2 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-8 leading-tight">
            {{ title }}
          </h2>
          <p class="text-xl md:text-2xl text-slate-300 mb-10 leading-relaxed">
            {{ subtitle }}
          </p>
          
          <div class="flex flex-col sm:flex-row gap-6 justify-center lg:justify-start">
            <ContactButton 
              :whatsappNumber="whatsappNumber"
              :whatsappMessage="whatsappMessage"
              size="large"
              variant="light"
            />
            
            <div class="flex items-center justify-center lg:justify-start gap-4 text-slate-400">
              <div class="flex items-center gap-2">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                </svg>
                <span class="text-sm">Respuesta inmediata</span>
              </div>
              <div class="flex items-center gap-2">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                </svg>
                <span class="text-sm">Sin compromiso</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Stats -->
        <div class="grid grid-cols-2 gap-8">
          <div class="text-center p-6 bg-white/10 backdrop-blur-sm rounded-2xl">
            <div class="text-4xl font-bold text-emerald-400 mb-2">500+</div>
            <div class="text-slate-300">Casos resueltos</div>
          </div>
          <div class="text-center p-6 bg-white/10 backdrop-blur-sm rounded-2xl">
            <div class="text-4xl font-bold text-emerald-400 mb-2">15+</div>
            <div class="text-slate-300">Años de experiencia</div>
          </div>
          <div class="text-center p-6 bg-white/10 backdrop-blur-sm rounded-2xl">
            <div class="text-4xl font-bold text-emerald-400 mb-2">98%</div>
            <div class="text-slate-300">Casos exitosos</div>
          </div>
          <div class="text-center p-6 bg-white/10 backdrop-blur-sm rounded-2xl">
            <div class="text-4xl font-bold text-emerald-400 mb-2">24h</div>
            <div class="text-slate-300">Tiempo de respuesta</div>
          </div>
        </div>
      </div>
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
