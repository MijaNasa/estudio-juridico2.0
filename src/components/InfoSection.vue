<template>
  <section id="servicios" class="py-20 md:py-32 bg-slate-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-5 gap-16 items-center">
        <!-- Content - ocupa 3 columnas -->
        <div class="lg:col-span-3 order-2 lg:order-1">
          <div class="max-w-2xl">
            <h2 class="text-4xl md:text-5xl font-bold text-slate-900 mb-8 leading-tight">
              {{ title }}
            </h2>
            <p class="text-xl text-slate-600 mb-10 leading-relaxed">
              {{ description }}
            </p>
            
            <!-- Services List con mejor diseño -->
            <div class="space-y-6">
              <h3 class="text-2xl font-semibold text-slate-900 mb-6">
                Te ayudamos en:
              </h3>
              <div class="grid md:grid-cols-2 gap-4">
                <div 
                  v-for="(service, index) in services" 
                  :key="index"
                  class="flex items-start gap-4 p-4 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow"
                >
                  <div class="flex-shrink-0 w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center mt-1">
                    <svg class="w-5 h-5 text-emerald-600" fill="currentColor" viewBox="0 0 20 20">
                      <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                    </svg>
                  </div>
                  <span class="text-slate-700 font-medium">{{ service }}</span>
                </div>
              </div>
            </div>
            
            <!-- CTA Button -->
            <div class="mt-10">
              <ContactButton 
                :whatsappNumber="whatsappNumber"
                :whatsappMessage="whatsappMessage"
                size="medium"
              />
            </div>
          </div>
        </div>
        
        <!-- Image - ocupa 2 columnas -->
        <div class="lg:col-span-2 order-1 lg:order-2">
          <div class="relative">
            <img 
              :src="image" 
              :alt="'Consulta legal especializada'"
              class="w-full h-[400px] md:h-[600px] object-cover rounded-2xl shadow-2xl"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-slate-900/30 to-transparent rounded-2xl"></div>
            
            <!-- Floating card -->
            <div class="absolute bottom-6 left-6 right-6 bg-white/95 backdrop-blur-sm p-6 rounded-xl shadow-lg">
              <div class="flex items-center gap-4">
                <div class="w-12 h-12 bg-emerald-100 rounded-full flex items-center justify-center">
                  <svg class="w-6 h-6 text-emerald-600" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd" />
                  </svg>
                </div>
                <div>
                  <p class="font-semibold text-slate-900">Asesoramiento especializado</p>
                  <p class="text-sm text-slate-600">Más de 500 casos resueltos exitosamente</p>
                </div>
              </div>
            </div>
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
  description: {
    type: String,
    required: true
  },
  services: {
    type: Array,
    required: true
  },
  image: {
    type: String,
    required: true
  },
  whatsappNumber: {
    type: String,
    default: ""
  },
  whatsappMessage: {
    type: String,
    default: ""
  }
})
</script>