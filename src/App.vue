<template>
  <div class="h-screen w-full bg-black overflow-hidden">
    <!-- Section Photos (page d'accueil) -->
    <div v-if="currentSection === 'photos'" class="h-full w-full flex flex-col">
      <!-- Zone dédiée au bento grid - 75% de l'écran -->
      <div class="flex-1 min-h-0">
        <PhotoGrid :photos="photos" />
      </div>
      
      <!-- Zone dédiée aux textes et contrôles - 25% de l'écran -->
      <div class="h-1/4 md:h-1/4 lg:h-1/5 min-h-[180px] md:min-h-[200px] bg-black border-t border-gray-800 flex flex-col">
        <!-- Titre -->
        <div class="bg-black py-2 md:py-3 px-3 md:px-4 border-b border-gray-700">
          <h2 class="text-white text-lg md:text-xl lg:text-2xl font-bold">Lumières de l’IUT : parcours nocturne</h2>
        </div>
        
        <!-- Contenu principal avec audio et texte -->
        <div class="flex-1 bg-black/90 py-2 md:py-3 px-3 md:px-4 flex flex-col justify-center">
          <div class="flex items-center flex-wrap md:flex-nowrap gap-2 md:gap-0">
            <!-- Icône de lecture/pause -->
            <button class="text-white mr-2 md:mr-3 hover:text-yellow-300 transition-colors flex-shrink-0" @click="toggleAudio">
              <svg v-if="!isPlaying" xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 9v6m4-6v6m7-3a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </button>
            
            <!-- Visualiseur d'onde sonore -->
            <div class="flex items-center h-6 md:h-8 mx-2 md:mx-3 flex-shrink-0">
              <div class="w-0.5 md:w-1 h-1.5 md:h-2 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
              <div class="w-0.5 md:w-1 h-2 md:h-3 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
              <div class="w-0.5 md:w-1 h-3 md:h-4 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
              <div class="w-0.5 md:w-1 h-4 md:h-6 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
              <div class="w-0.5 md:w-1 h-3 md:h-4 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
              <div class="w-0.5 md:w-1 h-1.5 md:h-2 bg-white mx-0.25 md:mx-0.5 rounded-full" :class="{'animate-pulse': isPlaying}"></div>
            </div>
            
            <!-- Timer audio -->
            <div class="text-gray-400 text-xs md:text-sm flex-shrink-0 mr-3">
              {{ formatTime(currentTime) }} / {{ formatTime(duration) }}
            </div>
            
            <!-- Texte -->
            <p class="text-white text-xs md:text-sm lg:text-base leading-relaxed flex-1 w-full md:w-auto">
              Une exploration visuelle et sonore de l’IUT de Villeurbanne à la tombée de la nuit. <br>
              Entre ombres et halos, passé et avenir, un hommage sensible à l’histoire, aux idées et à la lumière.
            </p>
          </div>
        </div>
        
        <!-- Contrôles de navigation -->
        <div class="py-2 md:py-3 px-3 md:px-4 flex items-center justify-center space-x-3 md:space-x-4 border-t border-gray-700">
          <button @click="prevSection" class="text-white hover:text-yellow-300 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
            </svg>
          </button>
          <div class="flex space-x-1">
            <button
              v-for="(section, index) in sections" 
              :key="section"
              @click="goToSection(section)"
              class="w-6 md:w-8 h-0.5 md:h-1 rounded-full transition-colors duration-300 hover:bg-yellow-300"
              :class="currentSection === section ? 'bg-yellow-400' : 'bg-gray-600'"
              :title="`Aller à la page ${index + 1}`"
            ></button>
          </div>
          <button @click="nextSection" class="text-white hover:text-yellow-300 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 md:h-6 md:w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
            </svg>
          </button>
        </div>
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
import { ref, onMounted, onBeforeUnmount } from 'vue';
import PhotoGrid from './components/PhotoGrid.vue';
import HistorySection from './components/HistorySection.vue';
import AchievementsSection from './components/AchievementsSection.vue';

// État pour la lecture audio
const isPlaying = ref(false);
let audioElement = null;
const currentTime = ref(0);
const duration = ref(0);
let timeUpdateInterval = null;

// Initialisation de l'élément audio
onMounted(() => {
  audioElement = new Audio('/audio/ambience.mp3'); // Chemin vers votre fichier audio
  
  // Ajouter des écouteurs d'événements pour mettre à jour l'état
  audioElement.addEventListener('ended', () => {
    isPlaying.value = false;
    clearInterval(timeUpdateInterval);
  });
  
  audioElement.addEventListener('pause', () => {
    isPlaying.value = false;
    clearInterval(timeUpdateInterval);
  });
  
  audioElement.addEventListener('play', () => {
    isPlaying.value = true;
    startTimeUpdate();
  });
  
  audioElement.addEventListener('loadedmetadata', () => {
    duration.value = audioElement.duration;
  });
  
  audioElement.addEventListener('durationchange', () => {
    duration.value = audioElement.duration;
  });
});

// Nettoyer les ressources audio lors de la destruction du composant
onBeforeUnmount(() => {
  if (audioElement) {
    audioElement.pause();
    audioElement.src = '';
    audioElement.remove();
    audioElement = null;
  }
  
  clearInterval(timeUpdateInterval);
});

// Fonction pour formater le temps en mm:ss
function formatTime(seconds) {
  if (isNaN(seconds) || seconds === 0) return '00:00';
  const mins = Math.floor(seconds / 60);
  const secs = Math.floor(seconds % 60);
  return `${mins < 10 ? '0' : ''}${mins}:${secs < 10 ? '0' : ''}${secs}`;
}

// Fonction pour démarrer la mise à jour du temps
function startTimeUpdate() {
  clearInterval(timeUpdateInterval);
  timeUpdateInterval = setInterval(() => {
    if (audioElement && !audioElement.paused) {
      currentTime.value = audioElement.currentTime;
    }
  }, 250); // Mise à jour 4 fois par seconde
}

// Fonction pour basculer la lecture audio
function toggleAudio() {
  if (!audioElement) return;
  
  if (isPlaying.value) {
    audioElement.pause();
  } else {
    audioElement.play().catch(error => {
      console.error("Erreur lors de la lecture audio:", error);
    });
  }
}

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

function goToSection(sectionName) {
  currentSection.value = sectionName;
}

// Données des photos (à remplacer par vos propres photos)
const photos = ref([
  {
    src: '/images/iut-nuit-1.jpg',
    alt: 'Parking vide de nuit éclairé par des lampadaires',
    title: 'Parking silencieux',
    caption: 'Le parking vide, calme sous les réverbères. Les lignes blanches guident les pas comme des veines lumineuses.'
  },
  {
    src: '/images/iut-nuit-2.jpg',
    alt: 'Bâtiment sombre éclairé par la lumière d’un bâtiment voisin',
    title: 'Veille lumineuse',
    caption: 'Un bâtiment dort, baigné par la lumière de son voisin. Comme si l’un veillait sur l’autre.'
  },
  {
    src: '/images/iut-nuit-3.jpg',
    alt: 'Entrée du campus de l\'IUT avec un panneau lumineux',
    title: 'Point de départ',
    caption: 'Le panneau éclaire la carte du lieu. Premier repère d’un voyage à travers la nuit.'
  },
  {
    src: '/images/iut-nuit-4.jpg',
    alt: 'Vue panoramique nocturne du parking et de l’entrée du campus',
    title: 'Panorama nocturne',
    caption: 'La nuit s’ouvre sur l’ensemble du campus. Des halos timides dessinent les contours familiers.'
  },
  {
    src: '/images/iut-nuit-5.jpg',
    alt: 'Lueur bleue discrète entre deux bâtiments la nuit',
    title: 'Lueur cachée',
    caption: 'Une lueur bleue filtre entre les murs. Discrète, presque magique – comme un murmure dans l’obscurité.'
  },
  {
    src: '/images/iut-nuit-6.jpg',
    alt: 'Parking sombre partiellement éclairé par une lumière lointaine',
    title: 'Ombres immobiles',
    caption: 'Le parking s’efface dans l’obscurité, à peine frôlé par une lumière timide. Le silence y est plus dense.'
  },
  {
    src: '/images/iut-nuit-7.jpg',
    alt: 'Arbres de nuit avec lumière projetée au sol',
    title: 'Clairière artificielle',
    caption: 'Les branches dorment au-dessus, tandis qu’au sol, la lumière trace un sentier irréel à travers les feuilles.'
  },
  {
    src: '/images/iut-nuit-8.jpg',
    alt: 'Couloir vitré de l’IUT illuminé la nuit',
    title: 'Passage de verre',
    caption: 'Un couloir de lumière traverse la nuit. Entre les vitres, le silence et les reflets parlent à voix basse.'
  }
]
);
</script>

<style>
@keyframes pulse {
  0%, 100% {
    height: var(--original-height);
  }
  50% {
    height: calc(var(--original-height) + 4px);
  }
}

.animate-pulse {
  animation: pulse 0.8s ease-in-out infinite;
  --original-height: 100%;
}
</style>

