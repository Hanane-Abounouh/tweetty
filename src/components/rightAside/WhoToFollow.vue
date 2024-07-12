<template>
  <div class="max-w-sm rounded-lg bg-blue-900 overflow-hidden shadow-lg m-4 mr-20">
    <div class="flex">
      <div class="flex-1 m-2">
        <h2 class="px-4 py-2 text-xl w-48 font-semibold text-white">Who to follow</h2>
      </div>
    </div>
    <hr class="border-gray-600">

    <!-- Premier profil à suivre -->
    <div class="flex flex-shrink-0">
      <div class="flex-1 ">
        <div class="flex items-center w-48">
         <UserProfile />
              
              <div>
                <button type="submit" class="bg-transparent hover:bg-blue-600 text-white font-semibold hover:text-white py-2 px-4 border border-white hover:border-transparent rounded-full">Follow</button>
              </div> 
        </div>
      </div>
    </div>
    <hr class="border-gray-600">

    <!-- Deuxième profil à suivre -->
   
    <hr class="border-gray-600">

   

   

    <!-- Voir plus -->
    <div class="flex">
      <div class="flex-1 p-4">
        <h2 class="px-4 ml-2 w-48 font-bold text-blue-400">Voir plus</h2>  
      </div>
    </div>
  </div>
</template>

<script>
import UserProfile from '../UserProfile.vue'; // Import the UserProfile component
export default {
    components: {
    UserProfile,
  
  },
};
</script>

<style scoped>
/* Styles spécifiques à WhoToFollow.vue */
</style>
