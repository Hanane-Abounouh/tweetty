<template>
  <div class="flex ">
   
      <template v-for="(icon, index) in icons" :key="index">
         <div class="flex-1  mr-2 py-2">
        <a href="#" @click="toggleLike(icon)" class="w-12 mt-1 group flex items-center text-gray-400 px-3 py-2 text-base leading-6 font-medium rounded-full hover:bg-gray-600 hover:text-white">
          <svg
            class="h-7 w-6"
            :class="{ 'text-red-600': icon.id === 3 && tweet.liked, 'text-white': icon.id === 3 && !tweet.liked }"
            :viewBox="icon.viewBox"
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2">
            <path :d="icon.path"></path>
          </svg>
        </a>
     
          </div>
          
      </template>
   
  </div>
  
    <div class="text-gray-600 text-sm  ">
     
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'MainIcons',
  props: {
    tweet: Object,
  },
  data() {
    return {
      icons: [
        { id: 1, viewBox: '0 0 24 24', path: 'M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z' },
        { id: 2, viewBox: '0 0 24 24', path: 'M7 16V4m0 0L3 8m4-4l4 4m6 0v12m0 0l4-4m-4 4l-4-4' },
        { id: 3, viewBox: '0 0 24 24', path: 'M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z' },
        { id: 4, viewBox: '0 0 24 24', path: 'M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-8l-4-4m0 0L8 8m4-4v12' },
        { id: 5, viewBox: '0 0 24 24', path: 'M8 4H6a2 2 0 00-2 2v12a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-2m-4-1v8m0 0l3-3m-3 3L9 8m-5 5h2.586a1 1 0 01.707.293l2.414 2.414a1 1 0 00.707.293h3.172a1 1 0 00.707-.293l2.414-2.414a1 1 0 01.707-.293H20' },
        { id: 6, viewBox: '0 0 24 24', path: 'M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z' },
      ],
    };
  },
  methods: {
    async toggleLike(icon) {
      if (icon.id === 3) {
        // Inverser l'état liked du tweet
        this.tweet.liked = !this.tweet.liked;

        // Mettre à jour le serveur JSON simulé avec axios
        try {
          const response = await axios.patch(`http://localhost:3000/tweets/${this.tweet.id}`, {
            liked: this.tweet.liked,
          });
          console.log(response.data); // Afficher la réponse du serveur
        } catch (error) {
          console.error('Erreur lors de la mise à jour du like:', error);
        }

        // Afficher un message console pour vérification
        if (this.tweet.liked) {
          this.tweet.likes++;
          console.log('Liked! New count:', this.tweet.likes);
        } else {
          this.tweet.likes--;
          console.log('Unliked! New count:', this.tweet.likes);
        }
      }
    }
  }
};
</script>

<style scoped>
.Nlikes{
   margin-top: -5%;
}
</style>

