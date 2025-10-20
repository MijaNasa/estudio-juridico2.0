<template>
    <nav class="fixed top-0 left-0 right-0 z-50 bg-white/95 backdrop-blur-sm border-b border-slate-200 transition-all duration-300">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0">
            <div class="flex items-center">
              <div class="w-8 h-8 rounded-lg flex items-center justify-center mr-3">
                <img src="../assets/imagenes/logojude.png" alt="Logo" class="w-full h-full object-contain">
              </div>
              <span class="text-xl font-bold text-slate-900">Estudio Jurídico</span>
            </div>
          </div>
  
          <!-- Desktop Navigation -->
          <div class="hidden md:block">
            <div class="ml-10 flex items-baseline space-x-8">
              <a href="#inicio" class="text-slate-700 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors">
                Inicio
              </a>
              <a href="#servicios" class="text-slate-700 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors">
                Servicios
              </a>
              <a href="#testimonios" class="text-slate-700 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors">
                Testimonios
              </a>
              <a href="#contacto" class="text-slate-700 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors">
                Contacto
              </a>
            </div>
          </div>
  
          <!-- CTA Button -->
          <div class="hidden md:block">
            <ContactButton 
              :whatsappNumber="whatsappNumber"
              :whatsappMessage="whatsappMessage"
              size="small"
            />
          </div>
  
          <!-- Mobile menu button -->
          <div class="md:hidden">
            <button 
              @click="toggleMobileMenu"
              class="inline-flex items-center justify-center p-2 rounded-md text-slate-700 hover:text-emerald-600 hover:bg-slate-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-emerald-500"
              :aria-expanded="mobileMenuOpen"
            >
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path v-if="!mobileMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>
        </div>
      </div>
  
      <!-- Mobile menu -->
      <div v-show="mobileMenuOpen" class="md:hidden bg-white border-t border-slate-200">
        <div class="px-2 pt-2 pb-3 space-y-1">
          <a href="#inicio" @click="closeMobileMenu" class="block px-3 py-2 text-base font-medium text-slate-700 hover:text-emerald-600 hover:bg-slate-50 rounded-md transition-colors">
            Inicio
          </a>
          <a href="#servicios" @click="closeMobileMenu" class="block px-3 py-2 text-base font-medium text-slate-700 hover:text-emerald-600 hover:bg-slate-50 rounded-md transition-colors">
            Servicios
          </a>
          <a href="#testimonios" @click="closeMobileMenu" class="block px-3 py-2 text-base font-medium text-slate-700 hover:text-emerald-600 hover:bg-slate-50 rounded-md transition-colors">
            Testimonios
          </a>
          <a href="#contacto" @click="closeMobileMenu" class="block px-3 py-2 text-base font-medium text-slate-700 hover:text-emerald-600 hover:bg-slate-50 rounded-md transition-colors">
            Contacto
          </a>
          <div class="px-3 py-2">
            <ContactButton 
              :whatsappNumber="whatsappNumber"
              :whatsappMessage="whatsappMessage"
              size="small"
            />
          </div>
        </div>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import ContactButton from './ContactButton.vue'
  
  defineProps({
    whatsappNumber: {
      type: String,
      default: ""
    },
    whatsappMessage: {
      type: String,
      default: "Hola, quiero consultar sobre mi caso"
    }
  })
  
  const mobileMenuOpen = ref(false)
  
  const toggleMobileMenu = () => {
    mobileMenuOpen.value = !mobileMenuOpen.value
  }
  
  const closeMobileMenu = () => {
    mobileMenuOpen.value = false
  }
  </script>