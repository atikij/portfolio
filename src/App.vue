<script setup>
import Footer from "@/components/Footer.vue";
import Menu from "@/components/Menu.vue";
import SkyStar from "@/components/SkyStar.vue";
import Preloader from './components/Preloader.vue';

import { ref, onMounted } from 'vue';
const loading = ref(true);

const simulateLoading = () => {
  setTimeout(() => {
    loading.value = false;
  }, 2000);
};

onMounted(() => {
  simulateLoading();
});
</script>

<template>
  <header>
    <div class="wrapper">
      <Menu/>
    </div>
  </header>
  <sky-star/>

  <main>

  </main>
  <Footer/>
</template>

<style scoped lang="scss">
header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 1rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
  }


  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  main {
    margin: 20px 20vw 0 20vw;
  }
}

main {
  padding: 0 1rem;
}
</style>
