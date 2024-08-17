<script setup>

</script>

<template>
  <div  class="card">
    <h2> <br> </h2>
    <button><a href="#footer">Scroll</a></button>
  </div>
  <footer id="footer">
    <div class="col col1">
      <h3>Portfolio</h3>
      <p>Made by atikij</p>
      <div class="social">
        <a href="https://github.com/atikij" target="_blank" class="link"><img src="https://cdn.icon-icons.com/icons2/2429/PNG/512/github_logo_icon_147285.png" alt="" /></a>
        <a href="https://t.me/daun2jj" target="_blank" class="link"><img src="https://cdn.icon-icons.com/icons2/2699/PNG/512/telegram_logo_icon_168692.png" alt="" /></a>
      </div>
      <p style="color: #818181; font-size: smaller">2024 © All Rights Reserved</p>
    </div>
    <div class="col col2">
      <p>About</p>
      <p>About</p>
      <p>About</p>
      <p>About</p>
    </div>
    <div class="backdrop"></div>
  </footer>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=IBM%20Plex%20Sans:500|IBM%20Plex%20Sans:300");

* {
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  background-color: black;
  color: white;
  font-family: "IBM Plex Sans";
  font-weight: 300;

  display: flex;
  flex-direction: column;

  align-items: center;
  height: 190vh;
  margin: 0;
  color: #d5d5d5;
  font-size: calc(0.3 * var(--m));
}

h2 {
  font-weight: 500;
  text-align: center;
  font-size: var(--m);
  margin: 0;
}

h3 {
  font-weight: 500;
  font-size: calc(0.6 * var(--m));
  margin: 0;
}

.card {
  height: calc(8 * var(--m));
  background: linear-gradient(120deg, #ff8064, #725bdc);
  color: black;
  border-radius: calc(0.5 * var(--m));
  margin: 20px 20vw 0 20vw; /* Добавляем отступ для main на экранах >= 1024px */

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: var(--m);

  position: sticky;  /* Фиксируем по центру экрана */
  top: 50%;         /* Смещение на 50% по вертикали */
  transition: transform 0.3s ease;  /* Плавное перемещение */
  z-index: 10;  /* Поверх всего остального */
}


button {
  background-color: #000;
  font-size: calc(0.4 * var(--m));
  border: none;
  color: #e5e5e5;
  font-family: "IBM Plex Sans";
  font-weight: 400;
  padding: calc(0.35 * var(--m)) calc(0.8 * var(--m));
  border-radius: calc(0.3 * var(--m));
}

footer {
  z-index: 500;
  width: 100%;
  height: 100vh;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: flex-end;
  padding: 5rem 2vw;
  position: relative;
}

footer::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
      rgba(0, 0, 0, 0) 5%,
      rgba(0, 0, 0, 0.3) 20%,
      rgba(0, 0, 0, 0.6) 30%,
      rgba(0, 0, 0, 0.8) 40%,
      rgba(0, 0, 0, 1) 50%,
      rgb(0, 0, 0)
  );
  z-index: -7;

}

.backdrop {
  z-index: -5;
  position: absolute;
  inset: 0;

  backdrop-filter: blur(40px);
  -webkit-backdrop-filter: blur(40px);

  mask-image: linear-gradient(
      rgba(0, 0, 0, 0),
      rgba(0, 0, 0, 0.5) 10%,
      rgba(0, 0, 0, 0.8) 20%,
      rgba(0, 0, 0, 1) 30%,
      rgb(0, 0, 0)
  );

}

.col {
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  padding: calc(0.3 * var(--m)) calc(0.8 * var(--m));
  width: 28%;
}

.col2, .col3 {
  background-color: #121212;
  border-radius: calc(0.5 * var(--m));
}

img {
  height: calc(0.3 * var(--m));
  object-fit: cover;
}

.social {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  gap: 1rem;
}

a {
  text-decoration: none;
  color: inherit;

}

p {
  margin-block-start: 1em;
  margin-block-end: 1em;
  font-size: calc(0.3 * var(--m));
  font-family: "IBM Plex Sans";
  font-weight: 300;
}

.link {
  width: calc(0.8 * var(--m));
  height: calc(0.8 * var(--m));
  background-color: rgba(255,255,255,0.1);
  border-radius: calc(0.1 * var(--m));

  display: flex;
  justify-content: center;
  align-items: center;
}


@media screen and (max-width: 1000px) {
  :root {
    --m: 3rem;
  }
}


@media screen and (max-width: 700px) {
  footer {
    flex-direction: column;
    padding: 5rem 20vw;
  }
  .col {
    width: 100%;
  }
}
</style>