<template>
  <div class="border border-gray-600 h-screen  border-t-0">
    <MainNavigation />
    <CreateTweet />
    <MainTweet />
  </div>
</template>

<script>
import MainNavigation from './MainNavigation.vue';
import CreateTweet from './CreateTweet.vue';
import MainTweet from './MainTweet.vue';

export default {
  components: {
    MainNavigation,
    CreateTweet,
    MainTweet
  }
};
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
