<script setup>
const continuar = [
  {
    name: "Glass Onion",
    year: "2022",
    image: "/glass-onion.jpg",
  },
  {
    name: "Emily the Criminal",
    year: "2022",
    image: "/emily.jpg",
  },
  {
    name: "Falling for Christmas",
    year: "2022",
    image: "/falling.jpg",
  },
  {
    name: "Watcher",
    year: "2022",
    image: "/watcher.jpg",
  },
];
</script>

<template>
  <h2 class="m-5 text-xl md:text-2xl font-semibold">Continuar Viendo</h2>
  <div class="carousel rounded-box">
    <div class="carousel-item pb-4 mr-3" v-for="item in continuar" :key="item.index">
      <div class="card card-compact w-72 md:w-80 lg:w-96 bg-base-100 shadow-lg">
        <figure><img :src="item.image" alt="poster" /></figure>
        <div class="card-body">
          <h2 class="card-title">{{ item.name }}</h2>
          <p class="lg:text-lg">{{ item.year }}</p>
          <div class="card-actions justify-end">
            <button class="btn btn-primary lg:text-lg">Seguir viendo</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
