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

// 3. Definição das Props adaptadas para o Card de Pacote
interface CardPacoteProps {
  duracao: string;
  titulo: string;
  corTitulo?: string; // Nova prop: Aceita cores em HEX (ex: '#CD7F32' para Bronze) ou classes
  precos: Precos; // Valor à vista
  precosParcelados: Precos; // Novo: Valor da parcela
  parcelas: string; // Novo: Quantidade de parcelas (ex: '5x')
  veiculoAtivo: "popular" | "suv" | "caminhonete";
  beneficios: Beneficio[];
}

// 4. Tornando as propriedades disponíveis no template
defineProps<CardPacoteProps>();
</script>

<template>
  <div
    class="group bg-ths-black hover:border-ths-green/30 relative flex flex-col overflow-hidden border border-neutral-800 p-6 transition-all duration-300"
  >
    <!-- Header: Título e Duração (Substitui a imagem) -->
    <div class="mb-6 flex items-center justify-between">
      <!-- O estilo inline garante que a cor passe independente de classes configuradas no Tailwind -->
      <h3
        class="text-xl font-black tracking-wide uppercase sm:text-2xl"
        :style="{ color: corTitulo || '#FFFFFF' }"
      >
        {{ titulo }}
      </h3>
      <div
        class="text-ths-green flex items-center gap-1.5 text-xs font-bold tracking-widest uppercase"
      >
        <svg
          class="h-4 w-4"
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

    <!-- Lista de Benefícios Dinâmica com novo ícone (Circle Check) -->
    <ul class="flex-1 space-y-3">
      <li
        v-for="(item, index) in beneficios"
        :key="index"
        class="flex items-start gap-2.5 text-sm text-neutral-300"
      >
        <svg
          class="text-ths-green mt-0.5 h-5 w-5 shrink-0"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
          />
        </svg>
        <span class="leading-tight">{{ item.texto }}</span>
      </li>
    </ul>

    <!-- Divider -->
    <div class="my-6 border-t border-neutral-800/80"></div>

    <!-- Footer: Preços & CTA Botão Cheio -->
    <div class="mt-auto flex flex-col gap-5">
      <!-- Bloco de Preços -->
      <div class="flex flex-col">
        <span
          class="mb-1 text-[10px] font-bold tracking-widest text-neutral-500 uppercase"
        >
          À vista
        </span>
        <span class="text-2xl font-black tracking-tight text-white sm:text-3xl">
          {{ precos[veiculoAtivo] }}
        </span>
        <span class="text-ths-green mt-1 text-sm font-bold">
          ou {{ parcelas }} de {{ precosParcelados[veiculoAtivo] }}
        </span>
      </div>

      <!-- Botão de Ação -->
      <button
        class="bg-ths-green hover:bg-ths-green/90 flex w-full items-center justify-center gap-2 rounded px-4 py-3.5 text-xs font-black tracking-widest text-black uppercase transition-all duration-200"
      >
        CONTRATAR PACOTE
        <svg
          class="h-3.5 w-3.5"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="3"
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
</template>
