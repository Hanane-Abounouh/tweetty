<template>
<div class="grid grid-cols-1 gap-4 p-12  pb-0">
    <!-- Avatar et Nom d'utilisateur -->
    <a href="#" class="flex-shrink-0 group block ">
      <div class="flex items-center">
        <div>
          <img class="inline-block h-10 w-10 rounded-full" src="https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png" alt="Avatar de l'utilisateur" />
        </div>
        <div class="ml-3">
          <p class="text-base leading-6 font-medium text-white">
            Sonali Hirave 
            <span class="text-sm leading-5 font-medium text-gray-400 group-hover:text-gray-300 transition ease-in-out duration-150">
             16 April
            </span>
          </p>
        </div>
      </div>
    </a>
  

  <div class="pl-16 mt-1">
    <!-- Contenu du Tweet -->
    <p class="text-base width-auto font-medium text-white flex-shrink">
      Day 07 of the challenge <span class="text-blue-400">#100DaysOfCode</span> 
      I was wondering what I can do with <span class="text-blue-400">#tailwindcss</span>, so just started building Twitter  UI using Tailwind and so far it looks so promising. I will post my code after completion.
      [07/100]
      <span class="text-blue-400"> #WomenWhoCode #CodeNewbie</span>
    </p>

    <!-- Image du Tweet -->
    <div class="md:flex-shrink pr-6 pt-6">
      <img class="rounded-lg w-full h-64" src="https://images.unsplash.com/photo-1556740738-b6a63e27c4df?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=448&q=80" alt="Image du tweet">
    </div>

    <!-- Icônes d'Interaction -->
    <div class="flex mt-4">
      <div class="w-full">                  
       <div class="flex items-center">
      <MainIcons />
    </div>
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
    MainIcons
  }
};
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
