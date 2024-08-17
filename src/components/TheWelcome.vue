<template>
  <div class="home">
    <div class="circle">
      <img src="https://avatars.githubusercontent.com/u/91220269?s=400&u=d94546aa589752fab2b810b34d4fd32bcaea6b40&v=4" alt="Profile Picture">
    </div>
    <div class="content">
      <h1>Привет</h1>
      <p>Меня зовут Никита и я Fullstack Developer из Москвы</p>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&display=swap');

body {
  font-family: "Comfortaa", sans-serif;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.home {
  color: #fff;
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
}

.circle {
  z-index: 0;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 2rem;
}

.circle img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.content {
  text-align: center;
}

h1 {
  font-family: "Comfortaa", sans-serif;
  font-size: 6rem;
  margin-bottom: 0.5rem;
}

p {
  font-family: "Comfortaa", sans-serif;
  font-size: 2rem;
  margin: 0;
}
</style>
