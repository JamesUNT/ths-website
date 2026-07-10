<template>
  <div class="w-full h-full">
    <section
      class="relative w-full h-full bg-cover bg-center bg-no-repeat bg-[url('/ths-bg-car.png')]"
    >
      <div class="absolute inset-0 bg-black/80">
        <div
          class="flex flex-col items-start gap-2 max-w-7xl mx-auto px-4 md:px-6 pt-10"
        >
          <div
            class="flex flex-row bg-ths-green/30 text-lg md:text-xl text-ths-green border-ths-green border p-2"
          >
            <MdiIcon icon="mdiHome" />
            <p>Atendimento 100% a domicílio</p>
          </div>

          <div
            class="flex flex-col *:text-6xl *:md:text-8xl uppercase font-bold text-white py-4"
          >
            <h1>Excelência</h1>
            <h1><span class="text-ths-green">em cada</span></h1>
            <h1>detalhe.</h1>
          </div>

          <div>
            <p
              class="text-gray-400 text-lg md:text-xl max-w-md leading-relaxed font-medium pb-4"
            >
              Levamos toda a estrutura até você - garagem, condomínio ou
              empresa. Sem fila, sem deslocamento.
            </p>
          </div>

          <div class="flex flex-row flex-wrap gap-4">
            <button
              class="flex flex-row gap-2 min-w-xs p-4 bg-ths-green text-black font-semibold uppercase"
            >
              <MdiIcon icon="mdiWhatsapp" />
              <p>Agendar pelo WhatsApp</p>
              <MdiIcon icon="mdiChevronRight" />
            </button>
            <div class="p-4 border border-gray-600/40">
              <NuxtLink
                class="text-white uppercase font-bold"
                to="/servicos-essenciais"
              >
                <p>Ver serviços</p>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="max-w-7xl mx-auto px-4 md:px-6 bg-ths-black py-8">
      <div class="flex flex-row items-center gap-2">
        <div class="h-0.5 w-6 bg-ths-green" />
        <p class="text-xs text-ths-green tracking-wider font-mono uppercase">
          Simples assim
        </p>
      </div>
      <div
        class="flex flex-col *:text-6xl *:md:text-8xl uppercase font-bold text-white py-2"
      >
        <h1>Como</h1>
        <h1><span class="text-ths-green">funciona</span></h1>
      </div>
    </section>
  </div>
</template>
