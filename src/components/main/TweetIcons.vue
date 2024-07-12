<template>
  <div>
    <div class="flex">
      <div
        v-for="(icon, index) in icons"
        :key="index"
        class="flex-1 text-center py-2 m-2"
      >
        <a
          href="#"
          class="mt-1 group flex items-center text-blue-400 px-2 py-2 text-base leading-6 font-medium rounded-full hover:bg-blue-600 hover:text-blue-50"
        >
          <svg
            class="text-center h-7 w-6"
            :fill="icon.fill"
            :stroke="icon.stroke"
            :viewBox="icon.viewBox"
          >
            <path :d="icon.d"></path>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TweetIcons',
  data() {
    return {
      icons: [
        {
          fill: 'none',
          stroke: 'currentColor',
          viewBox: '0 0 24 24',
          d: 'M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z',
        },
        {
          fill: 'none',
          stroke: 'currentColor',
          viewBox: '0 0 24 24',
          d: 'M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
        
        },
        {
          fill: 'none',
          stroke: 'currentColor',
          viewBox: '0 0 24 24',
          d: 'M16 8v8m-4-5v5m-4-2v2m-2 4h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z',
        },
        {
          fill: 'none',
          stroke: 'currentColor',
          viewBox: '0 0 24 24',
          d: 'M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Ajoutez ici les styles spécifiques à ce composant, si nécessaire */
</style>
