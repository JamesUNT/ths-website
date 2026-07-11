<template>
  <div class="grid h-screen grid-rows-[auto_1fr]">
    <header
      class="bg-opacity-80 z-50 w-full bg-black py-4 text-white shadow-md backdrop-blur-md"
    >
      <div
        class="mx-auto flex max-w-7xl flex-wrap items-center justify-between px-4 md:px-6"
      >
        <div
          class="flex items-center gap-2 font-mono text-xs tracking-wider text-gray-400 uppercase"
        >
          <NuxtImg sizes="sm:40px md:50px" format="svg" src="Logo-THS.svg" />
          <p>Estética a Domicílio</p>
        </div>

        <nav aria-label="Navegação principal desktop" class="hidden md:block">
          <ul
            class="flex flex-row gap-6 text-xs font-medium tracking-wider text-gray-400 uppercase"
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
            class="bg-ths-green flex flex-row items-center gap-1 p-2 font-semibold text-black uppercase"
          >
            <NuxtLink class="flex items-center gap-1" to="/agendar">
              <MdiIcon icon="mdiWhatsapp" />
            </NuxtLink>
          </div>

          <div class="md:hidden">
            <button
              @click="toggleMenu"
              class="flex items-center p-2 font-semibold text-white uppercase"
            >
              <MdiIcon :icon="!isMenuOpen ? 'mdiMenu' : 'mdiClose'" />
            </button>
          </div>
        </div>

        <div class="mt-4 w-full" :class="!isMenuOpen ? 'hidden' : 'block'">
          <nav aria-label="Navegação principal">
            <ul
              class="bg-ths-black flex flex-col items-start gap-2 font-medium *:ml-2 *:font-bold *:uppercase"
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
