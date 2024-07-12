<template>
  <div>
    <div class="flex px-9">
      <div class="m-2 w-10 py-1">
        <img class="inline-block h-10 w-10 rounded-full" src="https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png" alt="" />
      </div>
     <div class="flex-1 px-2 pt-2 mt-2">
          <textarea class=" bg-transparent text-gray-400 font-medium border  py-2 text-lg w-full" rows="2" cols="50" placeholder="  What's happening?"></textarea>
      </div>


    </div>
    <!--middle creat tweet below icons-->
    <div class="flex">
      <div class="w-10"></div>
      <div class="w-64 px-12">
        <TweetIcons />
      </div>
      <div class="flex-1">
        <button class="bg-blue-600 mt-5 hover:bg-blue-500 text-white font-bold py-2 px-8 rounded-full mr-8 float-right">
          Tweet
        </button>
      </div>
    </div>
    <hr class="border-blue-900 border-4">
  </div>
</template>

<script>
import TweetIcons from './TweetIcons.vue';

export default {
  name: 'CreateTweet',
  components: {
    TweetIcons,
  },
};
</script>

<style scoped>
/* Ajoutez ici les styles spécifiques à ce composant, si nécessaire */
</style>
