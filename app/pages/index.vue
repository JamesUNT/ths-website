<template>
  <div class="h-full w-full">
    <section
      class="relative h-full w-full bg-[url('/ths-bg-car.png')] bg-cover bg-center bg-no-repeat"
    >
      <div class="absolute inset-0 bg-black/80">
        <div
          class="mx-auto flex max-w-7xl flex-col items-start gap-2 px-4 pt-10 md:px-6"
        >
          <div
            class="bg-ths-green/30 text-ths-green border-ths-green flex flex-row border p-2 text-lg md:text-xl"
          >
            <MdiIcon icon="mdiHome" />
            <p class="text-ths-green font-mono tracking-widest uppercase">
              Atendimento 100% a domicílio
            </p>
          </div>

          <div
            class="flex flex-col py-4 font-bold text-white uppercase *:text-6xl *:md:text-8xl"
          >
            <h1>Excelência</h1>
            <h1><span class="text-ths-green">em cada</span></h1>
            <h1>detalhe.</h1>
          </div>

          <div>
            <p
              class="max-w-md pb-4 text-lg leading-relaxed font-medium text-gray-400 md:text-xl"
            >
              Levamos toda a estrutura até você - garagem, condomínio ou
              empresa. Sem fila, sem deslocamento.
            </p>
          </div>

          <div class="flex flex-row flex-wrap gap-4">
            <button
              class="bg-ths-green flex min-w-xs flex-row gap-2 p-4 font-semibold text-black uppercase"
            >
              <MdiIcon icon="mdiWhatsapp" />
              <p>Agendar pelo WhatsApp</p>
              <MdiIcon icon="mdiChevronRight" />
            </button>
            <div class="border border-gray-600/40 p-4">
              <NuxtLink
                class="font-bold text-white uppercase"
                to="/servicos-essenciais"
              >
                <p>Ver serviços</p>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="bg-ths-card">
      <section class="mx-auto max-w-7xl px-4 py-24 md:px-6">
        <div class="flex flex-row items-center gap-2">
          <div class="bg-ths-green h-0.5 w-6" />
          <p class="text-ths-green font-mono text-xs tracking-widest uppercase">
            Simples assim
          </p>
        </div>
        <div
          class="mt-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Como</h1>
          <h1><span class="text-ths-green">funciona</span></h1>
        </div>
        <div class="flex flex-col">
          <div class="mt-8 flex flex-row flex-wrap md:flex-nowrap md:*:w-1/4">
            <div
              class="bg-ths-black flex flex-col gap-2 border border-gray-600/40 p-4 md:border-t md:border-r-0"
            >
              <h3 class="text-ths-green text-2xl font-bold uppercase">01</h3>
              <h6 class="text-2xl font-bold text-white uppercase">
                escolha o serviço
              </h6>
              <p class="text-md text-gray-400">
                Fale com a gente pelo WhatsApp e descreva o que precisa para seu
                veículo.
              </p>
            </div>
            <div
              class="bg-ths-black flex flex-col gap-2 border border-t-0 border-gray-600/40 p-4 md:border-t md:border-r-0"
            >
              <h3 class="text-ths-green text-2xl font-bold uppercase">02</h3>
              <h6 class="text-2xl font-bold text-white uppercase">
                Agendamos o horário
              </h6>
              <p class="text-md text-gray-400">
                Você escolhe o dia e o horário. Trabalhamos de
                <span class="text-ths-green font-bold">segunda</span> a
                <span class="text-ths-green font-bold">sábado</span>.
              </p>
            </div>
            <div
              class="bg-ths-black flex flex-col gap-2 border border-t-0 border-gray-600/40 p-4 md:border-t md:border-r-0"
            >
              <h3 class="text-ths-green text-2xl font-bold uppercase">03</h3>
              <h6 class="text-2xl font-bold text-white uppercase">
                Chegamos até você
              </h6>
              <p class="text-md text-gray-400">
                Nossa equipe chega no endereço que você indicar - casa,
                condomínio ou empresa.
              </p>
            </div>
            <div
              class="bg-ths-black flex flex-col gap-2 border border-t-0 border-gray-600/40 p-4 md:border-t"
            >
              <h3 class="text-ths-green text-2xl font-bold uppercase">04</h3>
              <h6 class="text-2xl font-bold text-white uppercase">
                Carro novo, sem sair
              </h6>
              <p class="text-md text-gray-400">
                Você acompanha ou deixa com a gente, resultado garntido na sua
                porta.
              </p>
            </div>
          </div>
          <div
            class="bg-ths-card flex flex-row gap-2 border border-t-0 border-gray-600/40 p-4"
          >
            <div
              class="mx-auto flex w-10 flex-row justify-center md:items-center"
            >
              <MdiIcon class="text-ths-green" icon="mdiLightningBolt" />
            </div>
            <p class="text-sm text-gray-400">
              <span class="text-white"
                >Utilizamos a água e energia do local.</span
              >
              Todos os equipamentos, produtos e maquinário são nossos — o que
              precisamos de você é apenas o acesso a uma
              <span class="text-ths-green underline">tomada 127v</span> e a uma
              <span class="text-ths-green underline">fonte de água</span>. É
              assim que conseguimos manter o preço acessível e levar o serviço
              até a sua porta.
            </p>
          </div>
          <div
            class="bg-ths-green flex flex-col items-center justify-center gap-2 p-4 text-center md:flex-row md:justify-between"
          >
            <h1 class="text-3xl font-bold uppercase">
              Pronto ? É so chamar no WhatsApp.
            </h1>
            <button
              class="text-ths-green bg-ths-black flex items-center gap-1 p-4 font-bold uppercase"
            >
              <MdiIcon icon="mdiWhatsapp" />
              <p>Chamar agora</p>
              <MdiIcon icon="mdiChevronRight" />
            </button>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>
