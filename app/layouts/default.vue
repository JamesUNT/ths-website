<template>
  <div class="grid grid-rows-[auto_1fr] h-screen">
    <header
      class="z-50 bg-black text-white shadow-md backdrop-blur-md bg-opacity-80 py-4 w-full"
    >
      <div
        class="max-w-7xl mx-auto px-4 md:px-6 flex flex-wrap items-center justify-between"
      >
        <div
          class="flex gap-2 items-center text-xs font-mono text-gray-400 tracking-wider uppercase"
        >
          <NuxtImg sizes="sm:40px md:50px" format="svg" src="Logo-THS.svg" />
          <p>Estética a Domicílio</p>
        </div>

        <nav aria-label="Navegação principal desktop" class="hidden md:block">
          <ul
            class="flex flex-row gap-6 font-medium text-xs tracking-wider uppercase text-gray-400"
          >
            <li>
              <NuxtLink to="/" class="hover:text-ths-green transition-colors"
                >Como funciona</NuxtLink
              >
            </li>
            <li>
              <NuxtLink class="hover:text-ths-green transition-colors"
                >Serviços</NuxtLink
              >
            </li>
            <li>
              <NuxtLink class="hover:text-ths-green transition-colors"
                >Pacotes</NuxtLink
              >
            </li>
            <li>
              <NuxtLink class="hover:text-ths-green transition-colors"
                >Motos</NuxtLink
              >
            </li>
            <li>
              <NuxtLink class="hover:text-ths-green transition-colors"
                >Contato</NuxtLink
              >
            </li>
          </ul>
        </nav>

        <div class="flex flex-row items-center gap-2">
          <div
            class="flex flex-row items-center gap-1 bg-ths-green p-2 text-black font-semibold uppercase"
          >
            <NuxtLink class="flex items-center gap-1" to="/agendar">
              <MdiIcon icon="mdiWhatsapp" />
              <span class="hidden md:inline">Whatsapp</span>
            </NuxtLink>
          </div>

          <div class="md:hidden">
            <button
              @click="toggleMenu"
              class="p-2 text-white font-semibold uppercase flex items-center"
            >
              <MdiIcon :icon="!isMenuOpen ? 'mdiMenu' : 'mdiClose'" />
            </button>
          </div>
        </div>

        <div class="w-full mt-4" :class="!isMenuOpen ? 'hidden' : 'block'">
          <nav aria-label="Navegação principal">
            <ul
              class="bg-ths-black flex flex-col items-start font-medium gap-2 *:uppercase *:font-bold *:ml-2"
            >
              <li>
                <NuxtLink
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Como funciona</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Serviços</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Pacotes</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Motos</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Contato</NuxtLink
                >
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </header>

    <main class="overflow-y-auto">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>
