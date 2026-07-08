<template>
  <div class="bg-background text-on-surface font-body-md min-h-screen flex flex-col">
    <!-- TopAppBar -->
    <header class="bg-surface dark:bg-surface-dim border-b border-surface-container-highest dark:border-outline-variant sticky top-0 z-50">
      <div class="flex justify-between items-center w-full px-gutter max-w-container-max mx-auto h-16">
        <div class="flex items-center gap-md">
          <span class="font-display text-display-lg-mobile md:text-display-lg font-bold text-primary dark:text-primary-fixed-dim">Hitomoji Learn</span>
        </div>
        <nav class="hidden md:flex items-center gap-lg">
          <a class="text-on-surface-variant font-medium hover:text-primary transition-colors duration-200 cursor-pointer" href="#">Learn</a>
          <NuxtLink to="/practice" class="transition-colors duration-200 cursor-pointer" :class="route.path === '/practice' ? 'text-primary font-bold border-b-2 border-primary py-2' : 'text-on-surface-variant font-medium hover:text-primary py-2'">Practice</NuxtLink>
          <NuxtLink to="/" class="transition-colors duration-200 cursor-pointer" :class="route.path === '/' ? 'text-primary font-bold border-b-2 border-primary py-2' : 'text-on-surface-variant font-medium hover:text-primary py-2'">Generator</NuxtLink>
          <a class="text-on-surface-variant font-medium hover:text-primary transition-colors duration-200 cursor-pointer" href="#">Settings</a>
        </nav>
        <div class="flex items-center gap-md">
          <button class="material-symbols-outlined text-primary dark:text-primary-fixed-dim cursor-pointer p-sm hover:bg-surface-container rounded-full transition-opacity active:opacity-80">notifications</button>
          <button class="material-symbols-outlined text-primary dark:text-primary-fixed-dim cursor-pointer p-sm hover:bg-surface-container rounded-full transition-opacity active:opacity-80">account_circle</button>
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <main class="flex-grow w-full max-w-container-max mx-auto px-gutter py-xl pb-32 md:pb-xl">
      <slot />
    </main>

    <!-- Footer -->
    <footer class="w-full py-xl px-gutter flex flex-col items-center gap-md bg-surface-container-low dark:bg-surface-container-high mt-xl border-t border-surface-container-highest">
      <span class="font-headline-md text-headline-md font-bold text-primary">Hitomoji Learn</span>
      <div class="flex flex-wrap justify-center gap-lg">
        <a class="text-tertiary font-body-md hover:underline hover:text-on-surface transition-all duration-300" href="#">Privacy Policy</a>
        <a class="text-tertiary font-body-md hover:underline hover:text-on-surface transition-all duration-300" href="#">Terms of Service</a>
        <a class="text-tertiary font-body-md hover:underline hover:text-on-surface transition-all duration-300" href="#">Help Center</a>
        <a class="text-tertiary font-body-md hover:underline hover:text-on-surface transition-all duration-300" href="#">Language Settings</a>
      </div>
      <p class="text-tertiary font-body-md">© 2024 Hitomoji By SkalZ </p>
    </footer>

    <!-- Mobile Navigation Shell -->
    <nav class="md:hidden fixed bottom-0 left-0 w-full flex justify-around items-center py-2 px-4 pb-safe bg-surface-container-lowest dark:bg-surface-container border-t border-surface-container-highest shadow-sm z-50">
      <div class="flex flex-col items-center justify-center text-on-tertiary-fixed-variant hover:bg-surface-container-low transition-colors px-4 py-1 cursor-pointer">
        <span class="material-symbols-outlined">school</span>
        <span class="font-label-sm text-label-sm">Learn</span>
      </div>
      <NuxtLink to="/practice" class="flex flex-col items-center justify-center px-4 py-1 cursor-pointer" :class="route.path === '/practice' ? 'bg-primary-container text-on-primary-container rounded-full' : 'text-on-tertiary-fixed-variant hover:bg-surface-container-low'">
        <span class="material-symbols-outlined">exercise</span>
        <span class="font-label-sm text-label-sm">Practice</span>
      </NuxtLink>
      <NuxtLink to="/" class="flex flex-col items-center justify-center px-4 py-1 cursor-pointer" :class="route.path === '/' ? 'bg-primary-container text-on-primary-container rounded-full' : 'text-on-tertiary-fixed-variant hover:bg-surface-container-low'">
        <span class="material-symbols-outlined">auto_awesome</span>
        <span class="font-label-sm text-label-sm">Generator</span>
      </NuxtLink>
      <div class="flex flex-col items-center justify-center text-on-tertiary-fixed-variant hover:bg-surface-container-low transition-colors px-4 py-1 cursor-pointer">
        <span class="material-symbols-outlined">settings</span>
        <span class="font-label-sm text-label-sm">Settings</span>
      </div>
    </nav>
  </div>
</template>

<script setup lang="ts">
const route = useRoute()
</script>
