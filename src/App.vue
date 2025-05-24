<template>
  <div class="h-screen w-full bg-black overflow-hidden">
    <!-- Section Photos (page d'accueil) -->
    <div v-if="currentSection === 'photos'" class="h-full w-full">
      <!-- Utilisation du composant PhotoGrid avec style bento -->
      <PhotoGrid :photos="photos" />
      
      <!-- Zone de texte en bas avec titre et contenu -->
      <div class="absolute bottom-0 left-0 right-0 z-10">
        <!-- Titre -->
        <div class="bg-black py-2 px-4">
          <h2 class="text-white text-2xl font-bold">Entrée de l'IUT</h2>
        </div>
        
        <!-- Texte avec icônes -->
        <div class="bg-black/50 py-2">
          <div class="flex items-center px-4">
            <!-- Icône de lecture -->
            <button class="text-white mr-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </button>
            
            <!-- Visualiseur d'onde sonore -->
            <div class="flex items-center h-8 mx-2">
              <div class="w-1 h-2 bg-white mx-0.5 rounded-full"></div>
              <div class="w-1 h-3 bg-white mx-0.5 rounded-full"></div>
              <div class="w-1 h-4 bg-white mx-0.5 rounded-full"></div>
              <div class="w-1 h-6 bg-white mx-0.5 rounded-full"></div>
              <div class="w-1 h-4 bg-white mx-0.5 rounded-full"></div>
              <div class="w-1 h-2 bg-white mx-0.5 rounded-full"></div>
            </div>
            
            <!-- Texte -->
            <p class="text-white text-sm ml-4">Ici commence la marche. Les lampadaires veillent, silencieux, sur les idées perdues dans les feuilles.</p>
          </div>
        </div>
      </div>
      
      <!-- Contrôles de navigation -->
      <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex items-center space-x-4 z-20">
        <button @click="prevSection" class="text-white hover:text-yellow-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
          </svg>
        </button>
        <div class="flex space-x-1">
          <div class="w-8 h-1 bg-white rounded-full"></div>
          <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
          <div class="w-8 h-1 bg-gray-600 rounded-full"></div>
        </div>
        <button @click="nextSection" class="text-white hover:text-yellow-300">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>
    </div>
    
    <!-- Section Histoire -->
    <HistorySection 
      v-else-if="currentSection === 'history'" 
      :historical-image="'/images/iut-history.jpg'" 
      @prev="prevSection" 
      @next="nextSection" 
    />
    
    <!-- Section Exploits et Contributions -->
    <AchievementsSection 
      v-else-if="currentSection === 'achievements'" 
      @prev="prevSection" 
      @next="nextSection" 
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import PhotoGrid from './components/PhotoGrid.vue';
import HistorySection from './components/HistorySection.vue';
import AchievementsSection from './components/AchievementsSection.vue';

// Gestion de la navigation entre les sections
const sections = ['photos', 'history', 'achievements'];
const currentSection = ref('photos');

function nextSection() {
  const currentIndex = sections.indexOf(currentSection.value);
  const nextIndex = (currentIndex + 1) % sections.length;
  currentSection.value = sections[nextIndex];
}

function prevSection() {
  const currentIndex = sections.indexOf(currentSection.value);
  const prevIndex = (currentIndex - 1 + sections.length) % sections.length;
  currentSection.value = sections[prevIndex];
}

// Données des photos (à remplacer par vos propres photos)
const photos = ref([
  {
    src: '/images/iut-nuit-1.jpg', // À remplacer par le chemin de votre image
    alt: 'IUT de nuit',
    title: 'Entrée principale',
    caption: 'L\'entrée principale de l\'IUT illuminée dans la nuit',
    size: 'large-square'
  },
  {
    src: '/images/iut-nuit-2.jpg',
    alt: 'Allée de l\'IUT',
    title: 'Allée nocturne',
    caption: 'Les lampadaires veillent sur l\'allée principale',
    size: 'vertical-rectangle'
  },
  {
    src: '/images/iut-nuit-3.jpg',
    alt: 'Bâtiment de l\'IUT',
    title: 'Département informatique',
    caption: 'Façade du département informatique sous les étoiles',
    size: 'medium-square'
  },
  {
    src: '/images/iut-nuit-4.jpg',
    alt: 'Vue panoramique de l\'IUT',
    title: 'Panorama nocturne',
    caption: 'Vue d\'ensemble du campus dans la pénombre',
    size: 'wide-rectangle'
  },
  {
    src: '/images/iut-nuit-5.jpg',
    alt: 'Espace vert de l\'IUT',
    title: 'Jardin illuminé',
    caption: 'Les espaces verts baignés dans la lumière artificielle',
    size: 'small-square'
  },
  {
    src: '/images/iut-nuit-6.jpg',
    alt: 'Entrée secondaire',
    title: 'Porte des sciences',
    caption: 'L\'entrée du bâtiment des sciences exactes',
    size: 'horizontal-rectangle'
  },
  {
    src: '/images/iut-nuit-7.jpg',
    alt: 'Bibliothèque de nuit',
    title: 'Temple du savoir',
    caption: 'La bibliothèque universitaire, phare de connaissance dans l\'obscurité',
    size: 'tall-rectangle'
  },
  {
    src: '/images/iut-nuit-8.jpg',
    alt: 'Laboratoire de recherche',
    title: 'Recherche nocturne',
    caption: 'Les lumières du laboratoire de recherche ne s\'éteignent jamais',
    size: 'medium-square'
  },
]);
</script>

