<!-- src/components/Preloader.vue -->
<template>
  <div class="box">
    <div class="cube"></div>
    <div class="cube"></div>
    <div class="cube"></div>
    <div class="cube"></div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const loading = ref(true);

const simulateLoading = () => {
  setTimeout(() => {
    loading.value = false;
  }, 2000);
};

simulateLoading();
</script>

<style scoped lang="scss">
$c-white: #fff;
$c-black: #000;
$ani-dur: 3s;
$size: 50px;

@mixin fill {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.cube {
  position: absolute;
  width: 1em;
  height: 1em;
  background: #FED74C;
  animation: move $ani-dur ease-in-out infinite;
  // animation-play-state: paused;
  transform-style: preserve-3d;
  box-shadow: 5em 5em .3em .1em #DBDBDB;

  &::before,
  &::after {
    content: '';
    @include fill;
  }

  &::before {
    background-color: #C97431;
    transform-origin: 100% 100%;
    transform: rotateY(-90deg);
  }

  &::after {
    background-color: #E7A22B;
    transform-origin: 0% 100%;
    transform: rotateX(90deg);
  }

  @for $i from 1 through 4 {
    &:nth-of-type(#{$i}) {
      animation-delay: $ani-dur * ($i / 4 - 4);
    }
  }

  @keyframes move {
    0%,
    87.5%,
    100%  { transform: translate(1em, 0em); }
    12.5% { transform: translate(2em, 0em); }
    25%   { transform: translate(2em, 1em); }
    37.5%,
    50%   { transform: translate(1em, 1em); }
    62.5% { transform: translate(0em, 1em); }
    75%   { transform: translate(0em, 0em); }
  }
}

.box {
  @include fill;
  width: 3em;
  height: 2em;
  margin: 30vmin auto;
  font-size: $size;
  transform-style: preserve-3d;
  transform: rotateX(60deg) rotateZ(45deg);

  &:hover * { animation-play-state: paused; }
  &:active * { animation-play-state: running; }
}

/// reset
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  height: 100%;
}

body {
  display: flex;
  flex-direction: column;
  min-height: 100%;
  margin: 0;
  line-height: 1.4;
}

.intro {
  width: 90%;
  max-width: 50rem;
  padding-top: .5em;
  padding-bottom: 1rem;
  margin: 0 auto 1em;
  font-size: calc(1rem + 2vmin);
  text-transform: capitalize;
  text-align: center;
  font-family: serif;
  border-bottom: 1px dashed rgba(#000, .5);
}

.info {
  margin: auto 0 0;
  padding: 1em;
  font-size: .9em;
  font-style: italic;
  font-family: serif;
  text-align: right;
  opacity: .5;

  a {
    color: inherit;
  }
}

</style>
