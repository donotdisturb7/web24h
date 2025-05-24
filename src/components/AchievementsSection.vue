<template>
  <div class="h-full w-full flex flex-col bg-black text-white">
    <!-- Zone dédiée au contenu principal - SCROLLABLE -->
    <div class="flex-1 min-h-0 overflow-y-auto">
      <div class="relative w-full bg-black">
        <!-- Background lumineux subtil -->
        <div class="absolute inset-0 bg-gradient-to-tl from-yellow-900/5 via-black to-black"></div>
        
        <!-- Contenu principal -->
        <div class="relative z-10 px-4 md:px-8 lg:px-12 py-8 md:py-10 lg:py-12">
          <div class="max-w-5xl mx-auto">
            <!-- Grille des accomplissements -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8 lg:gap-10">
              
              <!-- Innovation -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">Innovation</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Des laboratoires qui repoussent les frontières du possible, 
                    éclairant la voie vers de nouvelles découvertes.
                  </p>
                </div>
              </div>

              <!-- Formation -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">Formation</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Des milliers de diplômés qui portent haut les valeurs de l'IUT, 
                    devenant des phares dans leurs domaines respectifs.
                  </p>
                </div>
              </div>

              <!-- Partenariats -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">Partenariats</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Une collaboration étroite avec l'industrie qui illumine 
                    la voie de l'innovation et du développement.
                  </p>
                </div>
              </div>

              <!-- Engagement -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">Engagement</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Un vecteur d'ascension sociale permettant à tous 
                    d'illuminer leur avenir professionnel.
                  </p>
                </div>
              </div>

              <!-- Recherche -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">Recherche</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Des équipes qui font briller l'IUT par leurs travaux, 
                    apportant des solutions aux défis contemporains.
                  </p>
                </div>
              </div>

              <!-- International -->
              <div class="group">
                <div class="space-y-4">
                  <div class="flex items-center space-x-3">
                    <div class="w-2 h-2 bg-yellow-400 rounded-full group-hover:scale-150 transition-transform duration-300"></div>
                    <h3 class="text-white text-base md:text-lg font-light">International</h3>
                  </div>
                  <p class="text-gray-400 text-sm leading-relaxed font-light pl-5">
                    Un réseau mondial qui fait rayonner l'excellence française 
                    bien au-delà des frontières.
                  </p>
                </div>
              </div>

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
          <h1 class="text-white text-lg md:text-xl lg:text-2xl font-light tracking-wide mb-1">Excellence</h1>
          <p class="text-yellow-400 text-sm font-light opacity-80">Rayonnement et innovation</p>
        </div>
      </div>
      
      <!-- Contenu principal avec citation -->
      <div class="flex-1 bg-black/90 py-2 md:py-3 px-3 md:px-4 flex flex-col justify-center">
        <div class="text-center">
          <div class="w-8 h-0.5 bg-yellow-400 mx-auto mb-3"></div>
          <blockquote class="text-white text-xs md:text-sm lg:text-base font-light italic leading-relaxed">
            "Dans l'obscurité de la nuit, l'IUT demeure un phare. 
            Ses lumières ne sont pas seulement celles de ses bâtiments, 
            mais celles de l'intelligence qui s'y épanouit."
          </blockquote>
        </div>
      </div>
      
      <!-- Contrôles de navigation -->
      <div class="py-2 md:py-3 px-3 md:px-4 flex items-center justify-center space-x-3 md:space-x-4 border-t border-gray-700">
        <button @click="$emit('prev')" class="text-gray-400 hover:text-yellow-400 transition-colors duration-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 19l-7-7 7-7" />
          </svg>
        </button>
        
        <div class="flex space-x-2">
          <div class="w-6 h-0.5 bg-gray-600 rounded-full"></div>
          <div class="w-6 h-0.5 bg-gray-600 rounded-full"></div>
          <div class="w-6 h-0.5 bg-yellow-400 rounded-full"></div>
        </div>
        
        <button @click="$emit('next')" class="text-gray-400 hover:text-yellow-400 transition-colors duration-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineEmits(['prev', 'next']);
</script>
