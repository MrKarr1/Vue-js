<script setup>
import { reactive, shallowRef } from 'vue';
import Navigation from './components/Navigation.vue';
import Home from './components/Home.vue';
import Footer from './components/Footer.vue';

const nav = shallowRef(Home);
const navi = (section, projetid) => {
  nav.value = section;
  projet.value = projetid;
  //console.log(projet.value);

}
const projet = reactive({})

</script>

<template>
  <div class="app-container">
    <Navigation @nav="navi" />
    <Transition name="fade" mode="out-in">
      <component @nav="navi" :is="nav" class="component" :projetprop="projet.value" />
    </Transition>

    <Footer @nav="navi" />
  </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  margin-left: 20%;
  margin-right: 20%;
  box-sizing: border-box;
}
</style>