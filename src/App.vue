<script setup>
import { ref } from 'vue';
import ImageGallery from './components/ImageGallery.vue';
import SideBar from './components/SideBar.vue';

const isGrayspace = ref(false);

const selectOption = (currentState) => {
  isGrayspace.value = currentState;
}
</script>

<template>
  <v-app>
    <SideBar @select-Option="selectOption" />
    <v-main>
      <!-- Cards -->
      <ImageGallery :is-grayspace="isGrayspace"/>
    </v-main>
  </v-app>
</template>
