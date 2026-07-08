<template>
  <div class="grid grid-rows-[auto_1fr] min-h-dvh">
    <header class="sticky top-0 z-50 w-full bg-black text-white shadow-md backdrop-blur-md bg-opacity-90 p-4">
      <div class=" grid grid-cols-[1fr_1fr_1fr_auto] gap-2 mx-auto items-center justify-between  text-gray-400">

        <div class="flex items-center gap-2 text-xs font-mono text-gray-400 tracking-wider uppercase">
          <NuxtImg sizes="sm:40px md:50px" format="svg" src="Logo-THS.svg"/>
          <p class="">Estética Automotiva</p>
        </div>

        <div class="col-start-3 flex flex-row">
          <div class="flex flex-row items-center gap-1 bg-ths-green px-2 py-2 text-black font-semibold uppercase">
            <MdiIcon icon="mdiWhatsapp"/>
            <NuxtLink 
              to="/agendar" 
            >
              whatsapp
            </NuxtLink>
          </div>
        </div>

        <div>
          <button @click="toggleMenu" class="px-2 py-2 text-white font-semibold uppercase">
            <MdiIcon :icon="!isMenuOpen ? 'mdiMenu' : 'mdiClose'"/>
          </button>
        </div>

        <div 
          class="col-span-full "
          :class="!isMenuOpen ? 'hidden' : ''"
        >
        
          <nav aria-label="Navegação principal">
            <ul class="flex flex-col font-medium text-center">
              <li>
                <NuxtLink to="/">Como funciona</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/servicos">Serviços</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/pacotes">Pacotes</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/motos">Motos</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/contato">Contato</NuxtLink>
              </li>
            </ul>
          </nav>
        </div>

      </div>
    </header>
    <main>
      <slot />
    </main>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>