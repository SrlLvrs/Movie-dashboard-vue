<script setup>
const destacadas = [
  {
    name: "Black Panther 2: Wakanda Forever",
    year: "2022",
    fanart: "/wakanda.jpg",
    rate: "7.3",
  },
  {
    name: "Enola Holmes 2",
    year: "2022",
    fanart: "/enola.jpg",
    rate: "7.5",
  },
];
</script>

<template>
  <h1 class="m-5 md:text-2xl text-xl font-semibold">Películas populares</h1>
  <div class="carousel rounded-box">
    <div class="md:text-xl lg:text-2xl carousel-item h-72 md:h-96 lg:h-[32rem] xl:h-[40rem] w-full bg-cover bg-center"
      v-for="item in destacadas" :key="item.index" :style="{ backgroundImage: `url(${item.fanart})` }">
      <!-- Título y botones -->
      <div class="grid grid-cols-2 gap-1 w-full text-slate-50">
        <!-- Columna izquierda: Título -->
        <div class="grid content-end p-3 lg:p-5">
          <p>
            <span class="font-semibold">{{ item.name }}</span><br />
            {{ item.year }}<br />
            <!-- IMDB LOGO -->
            <img class="relative bottom-0.5 mr-2 inline-block h-6 w-11" src="/imdb.svg" alt="imdb logo" />
            {{ item.rate }}
          </p>
        </div>
        <!-- Columna derecha: Botones -->
        <div class="grid grid-cols-2 content-end gap-2 p-3 lg:p-5">
          <button class="btn btn-primary text-xs md:text-base lg:text-lg">Ver ahora</button>
          <button class="btn btn-secondary text-xs md:text-base lg:text-lg">Descargar</button>
        </div>
      </div>
    </div>
  </div>
</template>
