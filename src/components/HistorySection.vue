<template>
  <div class="h-full w-full flex flex-col bg-black text-white">
    <!-- Zone dédiée au contenu principal - SCROLLABLE -->
    <div class="flex-1 min-h-0 overflow-y-auto">
      <div class="relative w-full bg-black">
        <!-- Background lumineux subtil -->
        <div class="absolute inset-0 bg-gradient-to-br from-yellow-900/10 via-black to-black"></div>
        
        <!-- Contenu principal -->
        <div class="relative z-10 px-4 md:px-8 lg:px-12 py-8 md:py-10 lg:py-12">
          <div class="max-w-4xl mx-auto grid lg:grid-cols-2 gap-8 lg:gap-12 items-center">
            <!-- Texte -->
            <div class="space-y-6 lg:space-y-8 order-2 lg:order-1">
              <div class="space-y-3">
                <div class="w-8 h-0.5 bg-yellow-400"></div>
                <h2 class="text-white text-lg md:text-xl lg:text-2xl font-light">Un phare de connaissance</h2>
                <p class="text-gray-300 text-sm md:text-base leading-relaxed font-light">
                  Depuis sa création, l'IUT de Lyon illumine le parcours de milliers d'étudiants. 
                  Chaque soir, ses fenêtres éclairées témoignent d'une activité intellectuelle 
                  qui ne s'arrête jamais.
                </p>
              </div>

              <div class="space-y-3">
                <div class="w-8 h-0.5 bg-yellow-400"></div>
                <h2 class="text-white text-lg md:text-xl lg:text-2xl font-light">Excellence nocturne</h2>
                <p class="text-gray-300 text-sm md:text-base leading-relaxed font-light">
                  Dans le silence de la nuit lyonnaise, l'IUT continue de briller. 
                  Ses laboratoires, ses salles d'étude, ses espaces de recherche 
                  forment une constellation de savoir qui guide les futures générations.
                </p>
              </div>

              <div class="space-y-3">
                <div class="w-8 h-0.5 bg-yellow-400"></div>
                <h2 class="text-white text-lg md:text-xl lg:text-2xl font-light">Rayonnement moderne</h2>
                <p class="text-gray-300 text-sm md:text-base leading-relaxed font-light">
                  Aujourd'hui, l'établissement perpétue sa mission : être une lumière 
                  dans l'obscurité de l'ignorance, un fanal d'innovation 
                  dans un monde en perpétuelle évolution.
                </p>
              </div>
            </div>

            <!-- Élément visuel minimaliste -->
            <div class="relative flex items-center justify-center order-1 lg:order-2 mb-6 lg:mb-0">
              <!-- Image principale -->
              <div class="relative w-48 h-60 sm:w-56 sm:h-72 md:w-64 md:h-80 lg:w-72 lg:h-96 rounded-lg overflow-hidden border border-gray-800">
                <img :src="historicalImage" alt="Histoire de l'IUT" class="w-full h-full object-cover">
                <div class=" inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent"></div>
              </div>
              
              <!-- Effets lumineux -->
              <div class="absolute -top-2 -left-2 w-3 h-3 md:w-4 md:h-4 bg-yellow-400 rounded-full opacity-60 animate-pulse"></div>
              <div class="absolute -bottom-2 -right-2 w-1.5 h-1.5 md:w-2 md:h-2 bg-yellow-400 rounded-full opacity-40"></div>
              <div class="absolute top-1/2 -right-3 md:-right-4 w-1 h-1 bg-yellow-400 rounded-full opacity-30"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Zone dédiée aux contrôles et titre - FIXED AT BOTTOM -->
    <div class="h-1/4 md:h-1/4 lg:h-1/5 min-h-[180px] md:min-h-[200px] bg-black border-t border-gray-800 flex flex-col">
      <!-- Titre -->
      <div class="bg-black py-2 md:py-3 px-3 md:px-4 border-b border-gray-700">
        <div class="border-l-2 border-yellow-400 pl-4">
          <h1 class="text-white text-lg md:text-xl lg:text-2xl font-light tracking-wide mb-1">Histoire</h1>
          <p class="text-yellow-400 text-sm font-light opacity-80">Les lumières du temps</p>
        </div>
      </div>
      
      <!-- Description - prend l'espace restant -->
      <div class="flex-1 bg-black/90 py-2 md:py-3 px-3 md:px-4 flex flex-col justify-center">
        <div class="flex items-center">
          <div class="w-2 h-2 bg-yellow-400 rounded-full mr-3 flex-shrink-0"></div>
          <p class="text-white text-xs md:text-sm lg:text-base leading-relaxed flex-1">
            L'histoire de l'IUT de Lyon s'écrit dans la lumière, entre tradition et innovation, 
            formant depuis des décennies les talents de demain.
          </p>
        </div>
      </div>
      
      <!-- Contrôles de navigation -->
      <div class="min-h-[50px] py-2 md:py-3 px-3 md:px-4 flex items-center justify-center space-x-3 md:space-x-4 border-t border-gray-700">
        <button @click="$emit('prev')" class="text-gray-400 hover:text-yellow-400 transition-colors duration-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 19l-7-7 7-7" />
          </svg>
        </button>
        
        <div class="flex space-x-1">
          <button 
            @click="$emit('goToSection', 0)" 
            class="w-6 md:w-8 h-0.5 md:h-1 rounded-full transition-colors duration-300 hover:bg-yellow-300"
            :class="false ? 'bg-yellow-400' : 'bg-gray-600'" 
            title="Aller à la page 1"
          ></button>
          <button 
            @click="$emit('goToSection', 1)" 
            class="w-6 md:w-8 h-0.5 md:h-1 rounded-full transition-colors duration-300 hover:bg-yellow-300"
            :class="true ? 'bg-yellow-400' : 'bg-gray-600'" 
            title="Aller à la page 2"
          ></button>
          <button 
            @click="$emit('goToSection', 2)" 
            class="w-6 md:w-8 h-0.5 md:h-1 rounded-full transition-colors duration-300 hover:bg-yellow-300"
            :class="false ? 'bg-yellow-400' : 'bg-gray-600'" 
            title="Aller à la page 3"
          ></button>
        </div>
        
        <button @click="$emit('next')" class="text-gray-400 hover:text-yellow-400 transition-colors duration-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineEmits(['prev', 'next', 'goToSection']);

const props = defineProps({
  historicalImage: {
    type: String,
    default: '/images/iut-nuit-3.jpg'
  }
});
</script>
