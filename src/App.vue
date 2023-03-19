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
    <RouterView v-slot="{Component}" class="view left-sidebar" name="LeftSideBar">
      <transition name="fade" mode="out-in">
        <component :is="Component" :key="$route.path"></component>
      </transition>
    </RouterView>
    <RouterView v-slot="{Component}" class="main-view">
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
  
  .container {
    display: flex;
  }
  .left-sidebar {
    width: 20%;
  }
  .main-view {
    width: 100%;
  }
</style>