<template>
  <div class="mb-4 flex flex-col items-end gap-3">
    <span class="font-mono text-xs tracking-widest text-neutral-400 uppercase">
      Tipo de Veículo
    </span>

    <div class="flex overflow-hidden rounded border border-neutral-800">
      <button
        @click="modeloAtivo = 'popular'"
        :class="[
          'px-6 py-2.5 text-xs font-black tracking-wider uppercase transition-colors',
          modeloAtivo === 'popular'
            ? 'bg-ths-green text-black'
            : 'text-neutral-400 hover:text-white',
        ]"
      >
        Popular
      </button>

      <button
        @click="modeloAtivo = 'suv'"
        :class="[
          'border-l border-neutral-800 px-6 py-2.5 text-xs font-black tracking-wider uppercase transition-colors',
          modeloAtivo === 'suv'
            ? 'bg-ths-green text-black'
            : 'text-neutral-400 hover:text-white',
        ]"
      >
        SUV
      </button>

      <button
        @click="modeloAtivo = 'caminhonete'"
        :class="[
          'border-l border-neutral-800 px-6 py-2.5 text-xs font-black tracking-wider uppercase transition-colors',
          modeloAtivo === 'caminhonete'
            ? 'bg-ths-green text-black'
            : 'text-neutral-400 hover:text-white',
        ]"
      >
        Caminhonete
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
type TipoVeiculo = "popular" | "suv" | "caminhonete";

const modeloAtivo = defineModel<TipoVeiculo>({ required: true });
</script>
