<script>
  //import { RouterLink, RouterView } from 'vue-router'
  import TheNavigation from '@/components/TheNavigation.vue'
  
  export default {
    components: {TheNavigation},
  }
</script>

<template>
  <TheNavigation></TheNavigation>
  <div class="container">
    <RouterView v-slot="{Component}" >
      <transition name="fade" mode="out-in">
        <component :is="Component" :key="$route.path"></component>
      </transition>
    </RouterView>
  </div>
</template>

<style>
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.4s;
  }
  
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
</style>