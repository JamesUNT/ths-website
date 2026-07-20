<script setup lang="ts">
// 1. Definição da interface para os itens da lista de benefícios
interface Beneficio {
  texto: string;
}

// 2. Definição da interface para o objeto de preços
interface Precos {
  popular: string;
  suv: string;
  caminhonete: string;
}

// 3. Definição das Props que o componente vai receber do pai
interface CardServicoProps {
  id: string;
  mostarId?: boolean;
  badge?: string;
  duracao: string;
  titulo: string;
  precos: Precos; // Recebe o objeto com os 3 preços
  veiculoAtivo: "popular" | "suv" | "caminhonete"; // Recebe qual a aba selecionada no momento
  imagemUrl: string;
  beneficios: Beneficio[];
}

// 4. Tornando as propriedades disponíveis no template
defineProps<CardServicoProps>();
</script>

<template>
  <div
    class="group bg-ths-black hover:border-ths-green/30 relative flex flex-col overflow-hidden border border-neutral-800 transition-all duration-300"
  >
    <!-- Top Image Section -->
    <div class="relative h-48 w-full overflow-hidden">
      <img
        :src="imagemUrl"
        :alt="titulo"
        class="h-full w-full object-cover object-center transition-transform duration-500 group-hover:scale-105"
      />
      <!-- Dark Overlays -->
      <div
        class="from-ths-black absolute inset-0 bg-linear-to-t via-transparent to-black/50"
      ></div>

      <!-- Top Badges Row -->
      <div
        class="absolute inset-x-0 top-0 flex items-center justify-between p-4"
      >
        <div class="flex items-center gap-2">
          <span
            v-show="mostarId"
            class="text-ths-green font-mono text-xs font-bold"
            >{{ id }}</span
          >
        </div>
        <div class="text-ths-green flex items-center gap-1 text-xs font-bold">
          <svg
            class="h-3.5 w-3.5"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2.5"
            stroke="currentColor"
          >
            <circle cx="12" cy="12" r="10" />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 6v6l4 2"
            />
          </svg>
          <span>{{ duracao }}</span>
        </div>
      </div>
    </div>

    <!-- Content Area -->
    <div class="flex flex-1 flex-col p-6 pt-3">
      <span
        v-if="badge"
        class="text-ths-green rounded py-0.5 text-[10px] font-bold tracking-wider uppercase"
      >
        {{ badge }}
      </span>
      <h3
        class="text-xl font-black tracking-wide text-white uppercase sm:text-2xl"
      >
        {{ titulo }}
      </h3>

      <!-- Lista de Benefícios Dinâmica -->
      <ul class="mt-4 flex-1 space-y-2.5">
        <li
          v-for="(item, index) in beneficios"
          :key="index"
          class="flex items-start gap-2.5 text-sm text-neutral-300"
        >
          <svg
            class="text-ths-green mt-0.5 h-4 w-4 shrink-0"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="3"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M4.5 12.75l6 6 9-13.5"
            />
          </svg>
          <span class="leading-tight">{{ item.texto }}</span>
        </li>
      </ul>

      <!-- Divider -->
      <div class="my-5 border-t border-neutral-800/80"></div>

      <!-- Footer: Preço & CTA -->
      <div class="mt-auto flex items-center justify-between">
        <!-- A MÁGICA ACONTECE AQUI: Buscamos o preço dinamicamente no objeto baseado na prop veiculoAtivo -->
        <span
          class="text-ths-green text-xl font-black tracking-tight sm:text-xl"
        >
          {{ precos[veiculoAtivo] }}
        </span>

        <button
          class="flex items-center gap-2 rounded border border-neutral-700 bg-transparent px-4 py-2 text-xs font-black tracking-widest text-white uppercase transition-all duration-200 hover:border-white hover:bg-white hover:text-black"
        >
          AGENDAR
          <svg
            class="h-3 w-3"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2.5"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M8.25 4.5l7.5 7.5-7.5 7.5"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>
