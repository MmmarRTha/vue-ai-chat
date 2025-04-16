<script setup lang="ts">
</script>

<template>
    <div class="flex items-center justify-center gap-4">
      <div class="flex gap-1">
        <!-- Small Star (Left) -->
        <svg class="w-3 h-3 sm:w-2 sm:h-2 animate-pulse" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2L15.5 8.5L22 12L15.5 15.5L12 22L8.5 15.5L2 12L8.5 8.5L12 2Z" stroke="url(#gradient)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M12 6L13.5 9.5L17 11L13.5 12.5L12 16L10.5 12.5L7 11L10.5 9.5L12 6Z" fill="url(#gradient)" opacity="0.5"/>
          <defs>
            <linearGradient id="gradient-small" x1="2" y1="2" x2="22" y2="22" gradientUnits="userSpaceOnUse">
              <stop stop-color="#D97706"/>
              <stop offset="1" stop-color="#EAB308"/>
            </linearGradient>
          </defs>
        </svg>
  
        <!-- Large Star (Middle) -->
        <svg class="w-8 h-8 sm:w-6 sm:h-6 animate-pulse" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2L15.5 8.5L22 12L15.5 15.5L12 22L8.5 15.5L2 12L8.5 8.5L12 2Z" stroke="url(#gradient)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M12 6L13.5 9.5L17 11L13.5 12.5L12 16L10.5 12.5L7 11L10.5 9.5L12 6Z" fill="url(#gradient)" opacity="0.5"/>
          <path d="M12 4L13.5 7.5L17 9L13.5 10.5L12 14L10.5 10.5L7 9L10.5 7.5L12 4Z" fill="url(#gradient)" opacity="0.3" class="animate-ping"/>
          <path d="M12 8L13.5 11.5L17 13L13.5 14.5L12 18L10.5 14.5L7 13L10.5 11.5L12 8Z" fill="url(#gradient)" opacity="0.2" class="animate-pulse"/>
          <defs>
            <linearGradient id="gradient" x1="2" y1="2" x2="22" y2="22" gradientUnits="userSpaceOnUse">
              <stop stop-color="#D97706"/>
              <stop offset="1" stop-color="#EAB308"/>
            </linearGradient>
          </defs>
        </svg>
  
        <!-- Small Star (Right) -->
        <svg class="w-2 h-2 sm:w-3 sm:h-3 animate-pulse" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2L15.5 8.5L22 12L15.5 15.5L12 22L8.5 15.5L2 12L8.5 8.5L12 2Z" stroke="url(#gradient)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M12 6L13.5 9.5L17 11L13.5 12.5L12 16L10.5 12.5L7 11L10.5 9.5L12 6Z" fill="url(#gradient)" opacity="0.5"/>
          <defs>
            <linearGradient id="gradient-small" x1="2" y1="2" x2="22" y2="22" gradientUnits="userSpaceOnUse">
              <stop stop-color="#D97706"/>
              <stop offset="1" stop-color="#EAB308"/>
            </linearGradient>
          </defs>
        </svg>
      </div>
  
      <h1 class="inline-block text-5xl sm:text-8xl font-bold bg-gradient-to-l from-amber-700 to-yellow-300 bg-clip-text text-transparent text-center my-6 sm:my-10">
        AI EchoBot
      </h1>
    </div>
  </template>