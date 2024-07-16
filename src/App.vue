<template>
  <div id="app" class=" min-h-screen w-full   flex flex-col lg:flex-row">
    <aside class="w-full lg:w-1/4 fixed z-10 ">
      <LeftMenu />
    </aside>
    <main class="w-full ml-96  overflow-auto   flex">
      <MainContent class=" w-3/4" />
    
        <RightMenu class="w-full lg:block mr-10   w-1/3" />
   
    </main>
  </div>
</template>

<script>
import LeftMenu from './components/leftAside.vue';
import MainContent from './components/main/MainContent.vue';
import RightMenu from './components/rightAside/RightMenu.vue';

export default {
  components: {
    LeftMenu,
    MainContent,
    RightMenu,
  },
};
</script>

<style>
#app {
  background-color: #15202b;
  width: 100%;
  height: 100%;
}

/* Ajoutez ici d'autres styles spécifiques au besoin */
</style>
