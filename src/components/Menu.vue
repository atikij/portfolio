<script setup>
import { onMounted, ref } from 'vue';

const nav = ref(null);
const indicator = ref(null);
const items = ref([]);

onMounted(() => {
  const itemElements = nav.value.querySelectorAll('.nav-item');

  function handleIndicator(el) {
    itemElements.forEach(item => {
      item.classList.remove('is-active');
      item.removeAttribute('style');
    });

    indicator.value.style.width = `${el.offsetWidth}px`;
    indicator.value.style.left = `${el.offsetLeft}px`;
    indicator.value.style.backgroundColor = el.getAttribute('active-color');

    el.classList.add('is-active');
    el.style.color = el.getAttribute('active-color');
  }

  itemElements.forEach(item => {
    item.addEventListener('click', (e) => { handleIndicator(e.target) });
    item.classList.contains('is-active') && handleIndicator(item);
  });

  const activeItem = nav.value.querySelector('.nav-item.is-active');
  if (activeItem) handleIndicator(activeItem);
});
</script>

<template>
  <nav ref="nav" class="nav">
    <a href="#" class="nav-item is-active" active-color="orange">Home</a>
    <a href="#" class="nav-item" active-color="green">About</a>
    <a href="#" class="nav-item" active-color="blue">Testimonials</a>
    <a href="#" class="nav-item" active-color="red">Blog</a>
    <a href="#" class="nav-item" active-color="rebeccapurple">Contact</a>
    <span ref="indicator" class="nav-indicator"></span>
  </nav>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=DM+Sans:500,700&display=swap');

* {
  box-sizing: border-box;
}

body {
  text-align: center;
  display: flex;
  height: 100vh;
  width: 100%;
  justify-content: center;
  align-items: center;
  padding: 0 20px;
  background-image: url("https://www.toptal.com/designers/subtlepatterns/patterns/debut_light.png");
}

.nav {
  display: inline-flex;
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  overflow: hidden;
  max-width: 100%;
  background-color: #fff;
  padding: 0 20px;
  border-radius: 40px;
  box-shadow: 0 10px 40px rgba(159, 162, 177, .8);
  z-index: 1000;
}

@media (max-width: 580px) {
  .nav {
    position: static;
    flex-wrap: wrap;
  }
}


.nav-item {
  color: #83818c;
  padding: 20px;
  text-decoration: none;
  transition: .3s;
  margin: 0 6px;
  z-index: 1;
  font-family: 'DM Sans', sans-serif;
  font-weight: 500;
  position: relative;
  cursor: pointer;

  &:before {
    content: "";
    position: absolute;
    bottom: -6px;
    left: 0;
    width: 100%;
    height: 5px;
    background-color: #dfe2ea;
    border-radius: 8px 8px 0 0;
    opacity: 0;
    transition: .3s;
  }
}

.nav-item:not(.is-active):hover:before {
  opacity: 1;
  bottom: 0;
}

.nav-item:not(.is-active):hover { color: #333; }

.nav-indicator {
  position: absolute;
  left: 0;
  bottom: 0;
  height: 4px;
  transition: .4s;
  height: 5px;
  z-index: 1;
  border-radius: 8px 8px 0 0;
}

@media (max-width: 580px) {
  .nav { overflow: auto; }
}
</style>
