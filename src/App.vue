<template>
  <div id="app" class="bg-dark min-h-screen flex bg-[#15202b]">
    <LeftMenu  />
    <main>
      <MainContent  />
    
    </main>
      <RightMenu  />
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
  }
};
</script>

<style>
#app {
   background-color: #15202b;
   height: 100%;
   width: 100%;
}
</style>
