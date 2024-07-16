<template>
  <div v-if="user" class="flex-shrink-0 flex  rounded-full p-4 mr-2">
    <a href="#" class="flex-shrink-0 group block">
      <div class="flex items-center">
        <div>
          <img v-if="user.imageUrl" class="inline-block h-10 w-10 rounded-full" :src="user.imageUrl" alt="User Image" />
          <div v-else class="inline-block h-10 w-10 rounded-full bg-gray-300 flex items-center justify-center">
            <svg class="h-6 w-6 text-gray-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </div> <!-- Placeholder or default image -->
        </div>
        <div class="ml-3">
          <p class="text-base leading-6 font-medium text-white">
            {{ user.name }}
          </p>
          <p class="text-sm leading-5 font-medium text-gray-400 group-hover:text-gray-300 transition ease-in-out duration-150">
            {{ user.username }}
          </p>
        </div>
      </div>
    </a>
  </div>
  <div v-else class="flex-shrink-0 flex hover:bg-blue-500 rounded-full p-4 mr-2">
    <p class="text-gray-500">Informations utilisateur non disponibles</p>
  </div>
</template>

<script>
export default {
  name: 'UserProfile',
  props: {
    user: {
      type: Object,
      required: true,
      default: {
        imageUrl: 'https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png',
        name: 'Hanane',
        username: '@002'
      }
    }
  }
};
</script>

<style scoped>
/* Styles spécifiques au composant UserProfile.vue */
</style>
