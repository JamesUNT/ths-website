<script setup lang="ts">
interface CardPassoProps {
  id: string;
  titulo: string;
  descricao: string;
}

defineProps<CardPassoProps>();
</script>

<template>
  <div
    class="bg-ths-black hover:border-ths-green/30 flex flex-col border border-neutral-800 p-6 transition-all duration-300"
  >
    <!-- Número do Passo -->
    <span class="text-ths-green mb-3 block font-mono text-base font-bold">
      {{ id }}
    </span>

    <!-- Título do Passo -->
    <h4
      class="mb-3 text-lg leading-tight font-black tracking-wide text-white uppercase"
    >
      {{ titulo }}
    </h4>

    <!-- Descrição (Suporta HTML caso queira usar span com classe verde) -->
    <p class="text-sm leading-relaxed text-neutral-400" v-html="descricao"></p>
  </div>
</template>
