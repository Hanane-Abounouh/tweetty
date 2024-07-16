<template>
  <div class="grid grid-cols-1 gap-4 p-12 pb-0">
    <!-- Avatar et Nom d'utilisateur -->
    <a href="#" class="flex-shrink-0 group block">
      <div class="flex items-center">
        <div>
          <img class="inline-block h-10 w-10 rounded-full" :src="tweet.user.avatar" alt="Avatar de l'utilisateur" />
        </div>
        <div class="ml-3">
          <p class="text-base leading-6 font-medium text-white">
            {{ tweet.user.name }}
            <span class="text-sm leading-5 font-medium text-gray-400 group-hover:text-gray-300 transition ease-in-out duration-150">
              {{ tweet.created_at }}
            </span>
          </p>
        </div>
      </div>
    </a>

    <div class="pl-16 mt-1">
      <!-- Contenu du Tweet -->
      <p class="text-base width-auto font-medium text-white flex-shrink">
        {{ tweet.content }}
        
      </p>
      <div class="md:flex-shrink pr-6 pt-3">
        <img v-if="tweet.image" class="h-80 w-100" :src="tweet.image" alt="" />
          </div>

      <!-- Icônes d'Interaction -->
      <div class="flex">
        <div class="w-full">
          <!-- Inclure le composant MainIcons pour gérer les interactions -->
          <MainIcons :tweet="tweet" />
        </div>
      </div>

    </div>

    <!-- Séparateur -->
    <hr class="border-gray-600 p-2">
  </div>
</template>

<script>
import MainIcons from './MainIcons.vue';

export default {
  name: 'MainTweet',
  components: {
    MainIcons,
  },
  props: {
    tweet: Object,
  },
  watch: {
    tweet: {
      handler(newValue, oldValue) {
        console.log('Tweet changed:', newValue);
      },
      deep: true,
    },
  },
};
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
