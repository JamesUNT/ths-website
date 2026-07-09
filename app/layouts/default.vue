<template>
  <div class="grid grid-rows-[auto_1fr] h-screen">
    <header
      class="z-50 bg-black text-white shadow-md backdrop-blur-md bg-opacity-80 py-4 w-full"
    >
      <div
        class="max-w-7xl mx-auto px-4 items-center grid grid-cols-[1fr_1fr_auto]"
      >
        <div
          class="flex gap-2 text-xs font-mono text-gray-400 tracking-wider uppercase"
        >
          <NuxtImg sizes="sm:40px md:50px" format="svg" src="Logo-THS.svg" />
          <p>Estética a Domicílio</p>
        </div>

        <div
          class="col-span-full row-start-3"
          :class="!isMenuOpen ? 'hidden' : 'block'"
        >
          <nav aria-label="Navegação principal">
            <ul class="flex flex-col font-medium text-center gap-4">
              <li>
                <NuxtLink
                  to="/"
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Como funciona</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/servicos"
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Serviços</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/pacotes"
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Pacotes</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/motos"
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Motos</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/contato"
                  @click="toggleMenu"
                  class="hover:text-ths-green block py-1"
                  >Contato</NuxtLink
                >
              </li>
            </ul>
          </nav>
        </div>

        <div class="flex flex-row items-center justify-end gap-2">
          <div
            class="flex flex-row items-center gap-1 bg-ths-green p-2 text-black font-semibold uppercase"
          >
            <NuxtLink to="/agendar"> <MdiIcon icon="mdiWhatsapp" /> </NuxtLink>
          </div>

          <div>
            <button
              @click="toggleMenu"
              class="p-2 text-white font-semibold uppercase"
            >
              <MdiIcon :icon="!isMenuOpen ? 'mdiMenu' : 'mdiClose'" />
            </button>
          </div>
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
