<template>
  <div 
    class="relative w-full h-screen overflow-hidden bg-black p-4" 
  >
    <div 
      class="bento-grid w-full h-full"
    >
      <div 
        v-for="(photo, index) in photos" 
        :key="index" 
        class="bento-item relative overflow-hidden rounded-xl transition-all duration-300 ease-in-out group hover:scale-[1.02] hover:shadow-lg hover:shadow-yellow-500/20" 
        :class="photo.size || 'normal'"
      >
        <img 
          :src="photo.src" 
          :alt="photo.alt" 
          class="w-full h-full object-cover"
        >
        <div 
          class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out flex flex-col justify-end p-4"
        >
          <h3 class="text-yellow-300 font-bold text-lg mb-1">{{ photo.title || photo.alt }}</h3>
          <p class="text-white text-sm">{{ photo.caption }}</p>
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
/* Nous utilisons du CSS personnalisé pour le style bento car c'est plus optimal */
.bento-grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: repeat(6, 1fr);
  gap: 1rem;
}

.bento-item {
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.bento-item.large-square {
  grid-column: span 3;
  grid-row: span 3;
}

.bento-item.medium-square {
  grid-column: span 2;
  grid-row: span 2;
}

.bento-item.small-square {
  grid-column: span 1;
  grid-row: span 1;
}

.bento-item.horizontal-rectangle {
  grid-column: span 3;
  grid-row: span 2;
}

.bento-item.vertical-rectangle {
  grid-column: span 2;
  grid-row: span 3;
}

.bento-item.wide-rectangle {
  grid-column: span 4;
  grid-row: span 2;
}

.bento-item.tall-rectangle {
  grid-column: span 2;
  grid-row: span 4;
}

@media (max-width: 768px) {
  .bento-grid {
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: minmax(120px, auto);
  }
  
  .bento-item {
    grid-column: span 1 !important;
    grid-row: span 1 !important;
  }
  
  .bento-item.large-square,
  .bento-item.wide-rectangle {
    grid-column: span 2 !important;
  }
}
</style>
