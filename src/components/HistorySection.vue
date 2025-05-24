<template>
  <div class="relative h-screen w-full bg-black overflow-hidden">
    <div class="absolute top-4 left-4 z-10">
      <h1 class="text-yellow-300 text-2xl font-bold">Histoire de l'IUT</h1>
      <p class="text-white text-sm">Les lumières du passé</p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 p-8 h-full">
      <div class="flex flex-col justify-center text-white">
        <h2 class="text-3xl font-bold mb-6 text-yellow-300">Les origines</h2>
        <p class="mb-6">L'IUT de Lyon a été fondé avec la vision d'apporter l'éducation technique supérieure à tous. Depuis sa création, l'établissement a été un véritable phare de connaissances, illuminant le parcours de milliers d'étudiants.</p>
        
        <h2 class="text-3xl font-bold mb-6 text-yellow-300">Une tradition d'excellence</h2>
        <p class="mb-6">Au fil des décennies, l'IUT s'est forgé une réputation d'excellence, formant des professionnels reconnus dans tous les secteurs de l'industrie et des services. Sa pédagogie innovante a toujours mis l'accent sur l'équilibre entre théorie et pratique.</p>
        
        <h2 class="text-3xl font-bold mb-6 text-yellow-300">Rayonnement international</h2>
        <p>Aujourd'hui, l'IUT de Lyon rayonne bien au-delà des frontières françaises, tissant des partenariats avec des institutions du monde entier et accueillant des étudiants internationaux attirés par sa réputation d'excellence.</p>
      </div>
      
      <div class="relative flex items-center justify-center">
        <div class="w-full h-3/4 bg-gray-800 rounded-lg overflow-hidden relative">
          <!-- Remplacer par une image historique -->
          <img :src="historicalImage" alt="Histoire de l'IUT" class="w-full h-full object-cover">
          <div class="absolute inset-0 bg-gradient-to-t from-black via-transparent to-transparent"></div>
        </div>
        
        <!-- Éléments décoratifs -->
        <div class="absolute -bottom-6 -right-6 h-48 w-48 bg-yellow-400 rounded-full opacity-20"></div>
        <div class="absolute -top-6 -left-6 h-24 w-24 bg-blue-400 rounded-full opacity-20"></div>
      </div>
    </div>
    
    <!-- Navigation -->
    <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex items-center space-x-4 z-10">
      <button @click="$emit('prev')" class="text-white hover:text-yellow-300">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
        </svg>
      </button>
      <div class="flex space-x-1">
        <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
        <div class="w-8 h-1 bg-white rounded-full"></div>
        <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
      </div>
      <button @click="$emit('next')" class="text-white hover:text-yellow-300">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

defineEmits(['prev', 'next']);

const props = defineProps({
  historicalImage: {
    type: String,
    default: '/images/iut-history.jpg'
  }
});
</script>
