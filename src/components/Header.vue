<script setup>
const destacadas = [
  {
    name: 'Enola Holmes 2 en v-for',
    poster: '../assets/enola.jpg',
    rate: '7.5',
  },
];
</script>

<template>
  <h1 class="m-5 text-xl font-semibold">Películas populares</h1>
  <div id="controls-carousel" class="relative" data-carousel="static">
    <!-- Carousel wrapper -->
    <div class="relative h-64 overflow-hidden">
      <!-- Item 1 -->
      <div class="hidden duration-700 ease-in-out" data-carousel-item>
        <img
          src="../assets/enola.jpg"
          class="absolute top-1/2 left-1/2 block w-auto -translate-x-1/2 -translate-y-1/2"
          alt="..."
        />
        <div class="grid grid-cols-2 gap-4 text-slate-50">
          <div class="z-[25] grid h-64 content-end p-3">
            <p>
              <span class="font-semibold">Enola Holmes 2</span><br />
              2022<br />
              <!-- IMDB LOGO -->
              <img
                class="relative bottom-0.5 mr-2 inline-block h-6 w-11"
                src="../assets/imdb.svg"
                alt="imdb logo"
              />
              7.5
            </p>
          </div>
          <div class="z-[25] grid grid-cols-2 content-end gap-1 p-3">
            <button
              type="button"
              class="rounded-lg bg-gradient-to-br from-green-400 to-blue-600 px-5 py-2.5 text-center text-sm font-medium text-white hover:bg-gradient-to-bl focus:outline-none focus:ring-4 focus:ring-green-200 dark:focus:ring-green-800"
            >
              Ver Ahora
            </button>
            <button
              type="button"
              class="rounded-lg bg-gradient-to-r from-purple-500 to-pink-500 px-5 py-2.5 text-center text-sm font-medium text-white hover:bg-gradient-to-l focus:outline-none focus:ring-4 focus:ring-purple-200 dark:focus:ring-purple-800"
            >
              Descargar
            </button>
          </div>
        </div>
      </div>
      <!-- Item 2 -->
      <div class="hidden duration-700 ease-in-out" data-carousel-item>
        <img
          src="../assets/foto-2.jpg"
          class="absolute top-1/2 left-1/2 block w-full -translate-x-1/2 -translate-y-1/2"
          alt="..."
        />
      </div>
      <!-- Item v-for -->
      <div
        v-for="item in destacadas"
        :key="item.index"
        class="hidden duration-700 ease-in-out"
        data-carousel-item
      >
        {{ item.name }}
        <img
          :src="item.poster"
          alt=""
          class="absolute top-1/2 left-1/2 block w-full -translate-x-1/2 -translate-y-1/2"
        />
      </div>
    </div>
    <!-- Slider controls -->
    <!-- Flecha Izquierda -->
    <button
      type="button"
      class="group absolute top-0 left-0 z-30 flex h-full cursor-pointer items-center justify-center px-4 focus:outline-none"
      data-carousel-prev
    >
      <span
        class="inline-flex h-10 w-10 items-center justify-center rounded-full bg-white/30 group-hover:bg-white/50 group-focus:outline-none group-focus:ring-4 group-focus:ring-white dark:bg-gray-800/30 dark:group-hover:bg-gray-800/60 dark:group-focus:ring-gray-800/70"
      >
        <svg
          aria-hidden="true"
          class="h-6 w-6 text-white dark:text-gray-800"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M15 19l-7-7 7-7"
          ></path>
        </svg>
        <span class="sr-only">Previous</span>
      </span>
    </button>
    <!-- Flecha derecha -->
    <button
      type="button"
      class="group absolute top-0 right-0 z-30 flex h-full cursor-pointer items-center justify-center px-4 focus:outline-none"
      data-carousel-next
    >
      <span
        class="inline-flex h-10 w-10 items-center justify-center rounded-full bg-white/30 group-hover:bg-white/50 group-focus:outline-none group-focus:ring-4 group-focus:ring-white dark:bg-gray-800/30 dark:group-hover:bg-gray-800/60 dark:group-focus:ring-gray-800/70"
      >
        <svg
          aria-hidden="true"
          class="h-6 w-6 text-white dark:text-gray-800"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M9 5l7 7-7 7"
          ></path>
        </svg>
        <span class="sr-only">Next</span>
      </span>
    </button>
  </div>
</template>
