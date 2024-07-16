<template >
  <div >
    <div class="flex px-9 ">
      <div class="m-2 w-10 py-1">
        <img class="inline-block h-10 w-10 rounded-full" src="https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png" alt="User Avatar" />
      </div>
      <div class="flex-1 px-2 pt-2 mt-2">
        <textarea v-model="newTweetContent" class="bg-transparent text-gray-400 font-medium border py-2 text-lg w-full" rows="2" cols="50" placeholder="  What's happening?"></textarea>
      </div>
    </div>
    <div class="flex">
      <div class="w-10"></div>
      <div class="w-64 px-12">
        <TweetIcons />
      </div>
      <div class="flex-1">
        <button @click="addTweet" :disabled="isPosting" class="bg-blue-600 mt-5 text-white font-bold py-2 px-8 rounded-full mr-8 float-right">
          Tweet
        </button>
      </div>
    </div>
    <hr class="border-blue-900 border-4" />
  </div>
</template>

<script>
import TweetIcons from './TweetIcons.vue';
import axios from 'axios';

export default {
  name: 'CreateTweet',
  components: {
    TweetIcons,
  },
  data() {
    return {
      newTweetContent: '',
      isPosting: false,
    };
  },
  methods: {
    addTweet() {
      if (!this.newTweetContent.trim()) {
        return;
      }

      this.isPosting = true;

      const newTweet = {
        content: this.newTweetContent,
        user: {
          avatar: 'https://pbs.twimg.com/profile_images/1121328878142853120/e-rpjoJi_bigger.png',
          name: 'Hanane',
        },
        created_at: this.formatDate(new Date()),
        retweets: 0,
        likes: 0,
        comments: 0,
        liked: false,
      };

      axios.post('http://localhost:3000/tweets', newTweet)
        .then(response => {
          this.$emit('tweet-added', response.data); // Emet le nouvel tweet ajouté
          this.newTweetContent = '';
        })
        .catch(error => {
          console.error('There was an error adding the tweet!', error);
        })
        .finally(() => {
          this.isPosting = false;
        });
    },
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' };
      return date.toLocaleDateString('en-US', options);
    },
  },
};
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
