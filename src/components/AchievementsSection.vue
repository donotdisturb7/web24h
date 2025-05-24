<template>
  <div class="relative h-screen w-full bg-black overflow-hidden">
    <div class="absolute top-4 left-4 z-10">
      <h1 class="text-white text-2xl font-bold">Exploits et Contributions</h1>
      <p class="text-white text-sm">Rayonnement de l'IUT</p>
    </div>
    
    <div class="grid grid-cols-2 md:grid-cols-3 gap-4 p-8 h-full items-center">
      <!-- Carte 1 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Innovation Technologique</h3>
        <p class="text-white text-sm">Les laboratoires de l'IUT ont contribué à des avancées significatives, éclairant la voie pour de nouvelles applications.</p>
      </div>
      
      <!-- Carte 2 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Formation d'Excellence</h3>
        <p class="text-white text-sm">Des milliers de diplômés ont porté haut les valeurs de l'IUT, devenant des lumières dans leurs domaines respectifs.</p>
      </div>
      
      <!-- Carte 3 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Partenariats Industriels</h3>
        <p class="text-white text-sm">L'étroite collaboration avec le tissu industriel a permis d'éclairer la voie de l'innovation et du développement régional.</p>
      </div>
      
      <!-- Carte 4 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Engagement Social</h3>
        <p class="text-white text-sm">L'IUT a toujours été un vecteur d'ascension sociale, permettant à des étudiants de tous horizons d'illuminer leur avenir.</p>
      </div>
      
      <!-- Carte 5 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 4a2 2 0 114 0v1a1 1 0 001 1h3a1 1 0 011 1v3a1 1 0 01-1 1h-1a2 2 0 100 4h1a1 1 0 011 1v3a1 1 0 01-1 1h-3a1 1 0 01-1-1v-1a2 2 0 10-4 0v1a1 1 0 01-1 1H7a1 1 0 01-1-1v-3a1 1 0 00-1-1H4a2 2 0 110-4h1a1 1 0 001-1V7a1 1 0 011-1h3a1 1 0 001-1V4z" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Recherche Appliquée</h3>
        <p class="text-white text-sm">Les équipes de recherche ont fait briller l'IUT par leurs travaux, apportant des solutions aux défis contemporains.</p>
      </div>
      
      <!-- Carte 6 -->
      <div class="bg-blue-900/30 p-4 rounded-lg border border-blue-700 hover:border-white transition-all duration-300 transform hover:scale-105">
        <div class="w-12 h-12 bg-white rounded-full mb-4 flex items-center justify-center text-blue-900">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        </div>
        <h3 class="text-lg font-bold mb-2 text-white">Rayonnement International</h3>
        <p class="text-white text-sm">L'IUT a tissé un réseau mondial de partenariats, faisant rayonner l'excellence française au-delà des frontières.</p>
      </div>
    </div>
    
    <!-- Navigation -->
    <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex items-center space-x-4 z-10">
      <button @click="$emit('prev')" class="text-white hover:text-white">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
        </svg>
      </button>
      <div class="flex space-x-1">
        <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
        <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
        <div class="w-8 h-1 bg-white rounded-full"></div>
      </div>
      <button @click="$emit('next')" class="text-white hover:text-white">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
import { defineEmits } from 'vue';

defineEmits(['prev', 'next']);
</script>
