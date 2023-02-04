<script setup>
import { onMounted } from "vue";
import { initCarousels } from "flowbite";

// Inicializar carrusel
onMounted(() => {
  initCarousels();
});

/* Para generar ambas columnas en el slide
el array está configurado por pares de películas. */
const dobles = [
  {
    peli1: {
      name: "Emily the Criminal",
      year: "2022",
      image: "/emily.jpg",
    },
    peli2: {
      name: "Falling for Christmas",
      year: "2022",
      image: "/falling.jpg",
    },
  },
  {
    peli1: {
      name: "Watcher",
      year: "2022",
      image: "/watcher.jpg",
    },
    /* Podría existir un número impar de películas, pues la 2da película se evalúa con v-if*/
  },
];
</script>

<template>
  <h2 class="m-5 text-lg font-semibold">Continuar Viendo</h2>
  <div class="relative" data-carousel="static">
    <!-- Carousel wrapper -->
    <div class="relative h-52 overflow-hidden">
      <!-- Item v-for -->
      <div
        v-for="item in dobles"
        :key="item.index"
        class="hidden duration-700 ease-in-out"
        data-carousel-item
      >
        <!-- Título y botones -->
        <div class="grid grid-cols-2 gap-4">
          <!-- Columna izquierda -->
          <div
            class="rounded-lg border border-gray-200 bg-white shadow dark:border-gray-700 dark:bg-gray-800"
          >
            <a href="#">
              <img class="rounded-t-lg" :src="item.peli1.image" />
            </a>
            <div class="px-3 pb-3">
              <p>
                <span class="font-semibold"> {{ item.peli1.name }}</span>
                <br />
                {{ item.peli1.year }}
              </p>
            </div>
          </div>
          <!-- Columna derecha -->
          <div
            v-if="item.peli2"
            class="rounded-lg border border-gray-200 bg-white shadow dark:border-gray-700 dark:bg-gray-800"
          >
            <a href="#">
              <img class="rounded-t-lg" :src="item.peli2.image" />
            </a>
            <div class="px-3 pb-3">
              <p>
                <span class="font-semibold"> {{ item.peli2.name }}</span>
                <br />
                {{ item.peli2.year }}
              </p>
            </div>
          </div>
        </div>
      </div>
      <!-- Slider controls -->
      <button
        type="button"
        class="group absolute top-0 left-0 z-30 flex h-full cursor-pointer items-center justify-center px-4 focus:outline-none"
        data-carousel-prev
      >
        <span
          class="inline-flex h-8 w-8 items-center justify-center rounded-full bg-white/30 group-hover:bg-white/50 group-focus:outline-none group-focus:ring-4 group-focus:ring-white dark:bg-gray-800/30 dark:group-hover:bg-gray-800/60 dark:group-focus:ring-gray-800/70 sm:h-10 sm:w-10"
        >
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-white dark:text-gray-800 sm:h-6 sm:w-6"
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
      <button
        type="button"
        class="group absolute top-0 right-0 z-30 flex h-full cursor-pointer items-center justify-center px-4 focus:outline-none"
        data-carousel-next
      >
        <span
          class="inline-flex h-8 w-8 items-center justify-center rounded-full bg-white/30 group-hover:bg-white/50 group-focus:outline-none group-focus:ring-4 group-focus:ring-white dark:bg-gray-800/30 dark:group-hover:bg-gray-800/60 dark:group-focus:ring-gray-800/70 sm:h-10 sm:w-10"
        >
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-white dark:text-gray-800 sm:h-6 sm:w-6"
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
  </div>
</template>
