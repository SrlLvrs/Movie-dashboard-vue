<script setup>
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
} from "@headlessui/vue";
import { Bars3Icon, XMarkIcon, HomeIcon, MagnifyingGlassIcon, HeartIcon, ArrowDownTrayIcon, Cog8ToothIcon } from "@heroicons/vue/24/outline";

const navigation = [
  { name: "Inicio", href: "#", current: true },
  { name: "Descubrir", href: "#", current: false },
  { name: "Favoritos", href: "#", current: false },
  { name: "Descargado", href: "#", current: false },
  { name: "Configuración", href: "#", current: false },
];
</script>

<template>
  <Disclosure as="nav" class="bg-gray-800" v-slot="{ open }">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Hamburguesa -->
          <DisclosureButton
            class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <!-- Navgación y logo -->
        <div
          class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="flex flex-shrink-0 items-center">
            <img
              class="block h-8 w-auto lg:hidden"
              src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=500"
              alt="Your Company"
            />
            <img
              class="hidden h-8 w-auto lg:block"
              src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=500"
              alt="Your Company"
            />
          </div>
          <!-- Navgación en sm y su -->
          <div class="hidden sm:ml-6 sm:block">
            <div class="flex space-x-4">
              <a
                v-for="item in navigation"
                :key="item.name"
                :href="item.href"
                :class="[
                  item.current
                    ? 'bg-gray-900 text-white'
                    : 'text-gray-300 hover:bg-gray-700 hover:text-white',
                  'rounded-md px-3 py-2 text-sm font-medium',
                ]"
                :aria-current="item.current ? 'page' : undefined"
                >{{ item.name }}</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Panel de navegación en vista móvil -->
    <DisclosurePanel class="sm:hidden">
      <div class="space-y-1 px-2 pt-2 pb-3">
        <DisclosureButton
          class="inline-flex w-full rounded-md bg-gray-900 px-4 py-2 text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
          <HomeIcon class="mr-2 h-5 w-5 text-white" aria-hidden="true" />
          Inicio
        </DisclosureButton>
        <DisclosureButton
          class="inline-flex w-full rounded-md px-4 py-2 text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
          <MagnifyingGlassIcon class="mr-2 h-5 w-5 text-white" aria-hidden="true" />
          Descubrir
        </DisclosureButton>
        <DisclosureButton
          class="inline-flex w-full rounded-md px-4 py-2 text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
          <HeartIcon class="mr-2 h-5 w-5 text-white" aria-hidden="true" />
          Favoritos
        </DisclosureButton>
        <DisclosureButton
          class="inline-flex w-full rounded-md px-4 py-2 text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
          <ArrowDownTrayIcon class="mr-2 h-5 w-5 text-white" aria-hidden="true" />
          Descargado
        </DisclosureButton>
        <DisclosureButton
          class="inline-flex w-full rounded-md px-4 py-2 text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
          <Cog8ToothIcon class="mr-2 h-5 w-5 text-white" aria-hidden="true" />
          Configuración
        </DisclosureButton>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<style scoped></style>
