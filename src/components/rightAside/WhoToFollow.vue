<template>
  <div class="max-w-sm md:max-w-lg xl:max-w-xl rounded-lg bg-blue-900 overflow-hidden shadow-lg m-4 md:mr-20">
    <div class="flex">
      <div class="flex-1 m-2">
        <h2 class="px-4 py-2 text-xl md:text-lg xl:text-xl font-semibold text-white">Who to follow</h2>
      </div>
    </div>
    <hr class="border-gray-600">

    <!-- Profils à suivre -->
    <div v-for="user in users" :key="user.id" class="flex flex-wrap items-center space-x-4 p-4">
      <UserProfile :user="user" />
      <div>
        <button @click="followUser(user)" class="bg-transparent hover:bg-blue-500 text-white font-semibold hover:text-white py-2 px-4 border border-white hover:border-transparent rounded-full">
          Follow
        </button>
      </div>
    </div>
    <hr class="border-gray-600">

    <!-- Voir plus -->
    <div class="flex">
      <div class="flex-1 p-4">
        <h2 class="px-4 ml-2 text-base md:text-lg xl:text-lg font-semibold text-blue-400">Show more</h2>
      </div>
    </div>
  </div>
</template>

<script>
import UserProfile from '@/components/UserProfile.vue';

export default {
  name: 'WhoToFollow',
  components: {
    UserProfile
  },
  data() {
    return {
      users: [
        { id: 1, imageUrl: 'https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png', name: 'marwa', username: '@marwalove' },
        { id: 2, imageUrl: 'https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png', name: 'hafsa', username: '@hafsa' },
        // Ajoutez d'autres utilisateurs à suivre ici si nécessaire
      ]
    };
  },
  methods: {
    followUser(user) {
      alert(`Following ${user.name}`);
      // Ajoutez ici la logique pour suivre un utilisateur
    }
  }
};
</script>

<style scoped>
/* Styles spécifiques à WhoToFollow.vue */
</style>
