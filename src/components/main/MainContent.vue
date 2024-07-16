<template>
  <div class="border border-gray-600 h-full border-t-0">
  
     <MainNavigation />
  
    <CreateTweet @tweet-added="handleNewTweet" />
    <div v-for="tweet in tweets" :key="tweet.id">
      <MainTweet :tweet="tweet" @update-tweet="updateTweet" />
    </div>
  </div>
</template>

<script>
import MainNavigation from './MainNavigation.vue';
import CreateTweet from './CreateTweet.vue';
import MainTweet from './MainTweet.vue';
import axios from 'axios';

export default {
  name: 'MainContent',
  components: {
    MainNavigation,
    CreateTweet,
    MainTweet,
  },
  data() {
    return {
      tweets: [],
    };
  },
  mounted() {
    this.fetchTweets();
  },
  methods: {
    fetchTweets() {
      axios.get('http://localhost:3000/tweets')
        .then(response => {
          this.tweets = response.data;
        })
        .catch(error => {
          console.error('Error fetching tweets:', error);
        });
    },
    handleNewTweet(newTweet) {
      this.tweets.unshift(newTweet);
    },
   
  },
};
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
