<template>
  <section id="testimonios" class="py-20 md:py-32 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-slate-900 mb-6">
          Lo que dicen nuestros clientes
        </h2>
        <p class="text-xl text-slate-600 max-w-3xl mx-auto">
          La confianza de nuestros clientes es nuestro mayor logro. Conocé las experiencias de quienes ya confiaron en nosotros.
        </p>
      </div>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 lg:gap-10">
        <div 
          v-for="(testimonial, index) in testimonials" 
          :key="index"
          class="bg-gradient-to-br from-slate-50 to-white p-8 rounded-2xl shadow-sm hover:shadow-xl transition-all duration-300 border border-slate-100 hover:border-emerald-200"
        >
          <!-- Stars -->
          <div class="flex gap-1 mb-6">
            <svg 
              v-for="star in testimonial.rating" 
              :key="star"
              class="w-6 h-6 text-yellow-400" 
              fill="currentColor" 
              viewBox="0 0 20 20"
            >
              <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
            </svg>
          </div>
          
          <!-- Testimonial Text -->
          <blockquote class="text-slate-700 mb-6 italic text-lg leading-relaxed">
            "{{ testimonial.text }}"
          </blockquote>
          
          <!-- Author -->
          <div class="flex items-center gap-4">
            <div class="w-12 h-12 bg-emerald-100 rounded-full flex items-center justify-center">
              <span class="text-emerald-600 font-semibold text-lg">{{ testimonial.name.charAt(0) }}</span>
            </div>
            <cite class="text-slate-900 font-semibold text-lg not-italic">
              {{ testimonial.name }}
            </cite>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  testimonials: {
    type: Array,
    required: true
  }
})
</script>