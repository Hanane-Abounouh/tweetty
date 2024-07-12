<template>
  
     <div class="flow-root m-6 inline">
    <div class="flex-1">
      <a href="#">
        <p class="text-sm leading-6 font-medium text-gray-400">Terms Privacy Policy Cookies Imprint Ads info</p>
      </a>
    </div>
    <div class="flex-2">
      <p class="text-sm leading-6 font-medium text-gray-300">{{ footerText }}</p>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear()
    };
  },
  methods: {
    getCompanyName() {
      return "Tweetty ";
    }
  },
  computed: {
    footerText() {
      return `© ${this.currentYear} ${this.getCompanyName()}. Tous droits réservés.`;
    }
  }
};
</script>

<style scoped>
/* Styles spécifiques au composant Footer.vue */
</style>
