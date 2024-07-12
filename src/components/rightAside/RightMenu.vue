<template>
   <div class="w-2/4 mr-14 h-auto bg-dark">
    <!-- Contenu du menu de droite -->
    <RightSearch />
    <TweetSection />
    <WhoToFollow />
    <RightFooter />
  </div>
</template>

<script>
import RightSearch from './RightSearch.vue';
import TweetSection from './TweetSection.vue';
import WhoToFollow from './WhoToFollow.vue';
import RightFooter from './RightFooter.vue';

export default {
  components: {
    RightSearch,
    TweetSection,
    WhoToFollow,
    RightFooter
  },
  // Logique spécifique au composant RightMenu.vue
};
</script>

<style scoped>
/* Styles spécifiques au composant RightMenu.vue */
</style>
