<template>
  <div 
    class="relative w-full h-full overflow-hidden bg-black p-2 md:p-4" 
  >
    <div 
      class="bento-grid w-full h-full"
    >
      <div 
        v-for="(photo, index) in photos" 
        :key="index" 
        class="bento-item relative overflow-hidden rounded-lg md:rounded-xl transition-all duration-300 ease-in-out group hover:scale-[1.02] hover:shadow-lg hover:shadow-yellow-500/20" 
        :class="`item-${index + 1}`"
      >
        <img 
          :src="photo.src" 
          :alt="photo.alt" 
          class="w-full h-full object-cover"
        >
        <div 
          class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/40 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out flex flex-col justify-end p-2 md:p-3"
        >
          <h3 class="text-yellow-300 font-bold text-xs md:text-sm lg:text-base mb-1 line-clamp-2">{{ photo.title || photo.alt }}</h3>
          <p class="text-white text-xs md:text-sm line-clamp-2 md:line-clamp-3 leading-relaxed">{{ photo.caption }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  photos: {
    type: Array,
    required: true
  }
});
</script>

<style scoped>
/* Layout bento optimisé avec CSS Grid */
.bento-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  grid-template-rows: repeat(8, 1fr);
  gap: 0.75rem;
  height: 100%;
}

.bento-item {
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3), 0 2px 4px -1px rgba(0, 0, 0, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.1);
}

/* Layout spécifique pour chaque élément - arrangement harmonieux sans superpositions */
.item-1 { 
  grid-column: 1 / 7; 
  grid-row: 1 / 5; 
}
.item-2 { 
  grid-column: 7 / 10; 
  grid-row: 1 / 4; 
}
.item-3 { 
  grid-column: 10 / 13; 
  grid-row: 1 / 3; 
}
.item-4 { 
  grid-column: 10 / 13; 
  grid-row: 3 / 5; 
}
.item-5 { 
  grid-column: 7 / 10; 
  grid-row: 4 / 6; 
}
.item-6 { 
  grid-column: 1 / 4; 
  grid-row: 5 / 9; 
}
.item-7 { 
  grid-column: 4 / 7; 
  grid-row: 5 / 9; 
}
.item-8 { 
  grid-column: 7 / 13; 
  grid-row: 6 / 9; 
}

/* Utilitaires pour limiter le texte */
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* Responsive design */
@media (max-width: 1024px) {
  .bento-grid {
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(8, 1fr);
  }
  
  .item-1 { grid-column: 1 / 4; grid-row: 1 / 4; }
  .item-2 { grid-column: 4 / 7; grid-row: 1 / 3; }
  .item-3 { grid-column: 4 / 7; grid-row: 3 / 5; }
  .item-4 { grid-column: 1 / 3; grid-row: 4 / 6; }
  .item-5 { grid-column: 3 / 5; grid-row: 4 / 6; }
  .item-6 { grid-column: 5 / 7; grid-row: 4 / 6; }
  .item-7 { grid-column: 1 / 4; grid-row: 6 / 9; }
  .item-8 { grid-column: 4 / 7; grid-row: 6 / 9; }
}

@media (max-width: 768px) {
  .bento-grid {
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(12, 1fr);
    gap: 0.5rem;
  }
  
  .item-1 { grid-column: 1 / 3; grid-row: 1 / 4; }
  .item-2 { grid-column: 1 / 2; grid-row: 4 / 6; }
  .item-3 { grid-column: 2 / 3; grid-row: 4 / 6; }
  .item-4 { grid-column: 1 / 2; grid-row: 6 / 8; }
  .item-5 { grid-column: 2 / 3; grid-row: 6 / 8; }
  .item-6 { grid-column: 1 / 3; grid-row: 8 / 10; }
  .item-7 { grid-column: 1 / 2; grid-row: 10 / 12; }
  .item-8 { grid-column: 2 / 3; grid-row: 10 / 12; }
}

@media (max-width: 480px) {
  .bento-grid {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(10, 1fr);
  }
  
  .item-1 { grid-column: 1 / 2; grid-row: 1 / 3; }
  .item-2 { grid-column: 1 / 2; grid-row: 3 / 4; }
  .item-3 { grid-column: 1 / 2; grid-row: 4 / 5; }
  .item-4 { grid-column: 1 / 2; grid-row: 5 / 6; }
  .item-5 { grid-column: 1 / 2; grid-row: 6 / 7; }
  .item-6 { grid-column: 1 / 2; grid-row: 7 / 8; }
  .item-7 { grid-column: 1 / 2; grid-row: 8 / 9; }
  .item-8 { grid-column: 1 / 2; grid-row: 9 / 10; }
}
</style>
