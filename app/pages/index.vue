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
            <!--TODO: 
              Diminuir o tamanho da fonte no mobile;
              deixar o background verde mais opaco. 
            -->
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
          class="my-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Como</h1>
          <h1><span class="text-ths-green">funciona</span></h1>
        </div>
        <div class="grid grid-cols-1">
          <!-- Grid de Passos (Mobile: 1 coluna | Tablet: 2 colunas | Desktop: 4 colunas) -->
          <div
            class="grid border-collapse grid-cols-1 gap-0 sm:grid-cols-2 lg:grid-cols-4"
          >
            <CustomCardPasso
              v-for="passo in passosComoFunciona"
              :key="passo.id"
              v-bind="passo"
            />
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
    <div class="bg-ths-black">
      <section class="mx-auto max-w-7xl px-4 py-24 md:px-6">
        <div class="flex flex-row items-center gap-2">
          <div class="bg-ths-green h-0.5 w-6" />
          <p class="text-ths-green font-mono text-xs tracking-widest uppercase">
            Todos a domicílio
          </p>
        </div>
        <div
          class="mt-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Serviços</h1>
          <h1><span class="text-ths-green">Essenciais</span></h1>
        </div>
        <div
          class="mt-2 flex flex-row flex-wrap md:flex-nowrap md:justify-between"
        >
          <p
            class="max-w-md pb-4 text-lg leading-relaxed font-medium text-gray-400 md:text-xl"
          >
            Cuidados fundamentais para manter o seu veículo sempre impecável.
          </p>
          <div class="mx-auto md:mx-0">
            <SeletorVeiculo v-model="veiculoSelecionado" />
          </div>
        </div>

        <div class="mt-8 grid grid-cols-1 md:grid-cols-2">
          <CustomCardServico
            v-for="servico in servicosPrincipais"
            :key="servico.id"
            :id="servico.id"
            :duracao="servico.duracao"
            :titulo="servico.titulo"
            :imagemUrl="servico.imagemUrl"
            :precos="servico.precos"
            :beneficios="servico.beneficios"
            :veiculoAtivo="veiculoSelecionado"
          />
        </div>
      </section>
    </div>
    <div class="bg-ths-card">
      <section class="mx-auto max-w-7xl px-4 py-24 md:px-6">
        <div class="flex flex-row items-center gap-2">
          <div class="bg-ths-green h-0.5 w-6" />
          <p class="text-ths-green font-mono text-xs tracking-widest uppercase">
            Corrija e Proteja
          </p>
        </div>
        <div
          class="mt-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Polimento</h1>
          <h1><span class="text-ths-green">e Proteção</span></h1>
        </div>
        <div
          class="mt-4 flex flex-row flex-wrap md:flex-nowrap md:justify-between"
        >
          <p
            class="max-w-md pb-4 text-lg leading-relaxed font-medium text-gray-400 md:text-xl"
          >
            Corrija as imperfeições, proteja o que importa.
          </p>
          <div class="mx-auto md:mx-0">
            <SeletorVeiculo v-model="veiculoSelecionado" />
          </div>
        </div>

        <div class="mt-8 grid grid-cols-1 md:grid-cols-3">
          <CustomCardServico
            v-for="servico in servicosEspecializados"
            :key="servico.id"
            :id="servico.id"
            :badge="servico.badge"
            :duracao="servico.duracao"
            :titulo="servico.titulo"
            :imagemUrl="servico.imagemUrl"
            :precos="servico.precos"
            :beneficios="servico.beneficios"
            :veiculoAtivo="veiculoSelecionado"
          />
        </div>
      </section>
    </div>
    <div class="bg-ths-black">
      <section class="mx-auto max-w-7xl px-4 py-24 md:px-6">
        <div class="flex flex-row items-center gap-2">
          <div class="bg-ths-green h-0.5 w-6" />
          <p class="text-ths-green font-mono text-xs tracking-widest uppercase">
            Economia e Resultado
          </p>
        </div>
        <div
          class="mt-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Pacotes</h1>
          <h1><span class="text-ths-green">THS</span></h1>
        </div>
        <div
          class="mt-2 flex flex-row flex-wrap md:flex-nowrap md:justify-between"
        >
          <p
            class="max-w-md pb-4 text-lg leading-relaxed font-medium text-gray-400 md:text-xl"
          >
            Combine serviços e economize. Parcelamento disponível.
          </p>
          <div class="mx-auto md:mx-0">
            <SeletorVeiculo v-model="veiculoSelecionado" />
          </div>
        </div>

        <div class="mt-8 grid grid-cols-1 md:grid-cols-3">
          <CustomCardPacote
            v-for="pacote in servicosPacotes"
            :key="pacote.id"
            :titulo="pacote.titulo"
            :corTitulo="pacote.corTitulo"
            :duracao="pacote.duracao"
            :parcelas="pacote.parcelas"
            :veiculoAtivo="veiculoSelecionado"
            :precos="pacote.precos"
            :precosParcelados="pacote.precosParcelados"
            :beneficios="pacote.beneficios"
          />
        </div>
      </section>
    </div>
    <div class="bg-ths-card">
      <section class="mx-auto max-w-7xl px-4 py-24 md:px-6">
        <div class="flex flex-row items-center gap-2">
          <div class="bg-ths-green h-0.5 w-6" />
          <p class="text-ths-green font-mono text-xs tracking-widest uppercase">
            Também atendemos
          </p>
        </div>
        <div
          class="mt-8 flex flex-col font-bold text-white uppercase *:text-6xl *:md:text-8xl"
        >
          <h1>Serviços para</h1>
          <h1><span class="text-ths-green">Motos</span></h1>
        </div>
        <div
          class="mt-4 flex flex-row flex-wrap md:flex-nowrap md:justify-between"
        >
          <p
            class="max-w-md pb-4 text-lg leading-relaxed font-medium text-gray-400 md:text-xl"
          >
            Cuidados que mantêm sua moto com brilho e aparência de nova.
          </p>
        </div>

        <div class="mt-8 grid grid-cols-1 md:grid-cols-3">
          <CustomCardServico
            v-for="servico in servicosMotos"
            :key="servico.id"
            :id="servico.id"
            :duracao="servico.duracao"
            :titulo="servico.titulo"
            :imagemUrl="servico.imagemUrl"
            :precos="servico.precos"
            :beneficios="servico.beneficios"
            :veiculoAtivo="veiculoSelecionado"
          />
        </div>
      </section>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

type TipoVeiculo = "popular" | "suv" | "caminhonete";
const veiculoSelecionado = ref<TipoVeiculo>("popular");

const passosComoFunciona = [
  {
    id: "01",
    titulo: "Escolha o Serviço",
    descricao:
      "Fale com a gente pelo WhatsApp e descreva o que precisa para seu veículo.",
  },
  {
    id: "02",
    titulo: "Agendamos o Horário",
    descricao:
      'Você escolhe o dia e o horário. Trabalhamos de <span class="text-ths-green font-bold">segunda a sábado</span>.',
  },
  {
    id: "03",
    titulo: "Chegamos até Você",
    descricao:
      "Nossa equipe chega no endereço que você indicar – casa, condomínio ou empresa.",
  },
  {
    id: "04",
    titulo: "Carro Novo, Sem Sair de Casa",
    descricao:
      "Você acompanha ou deixa com a gente, resultado garantido na sua porta.",
  },
];
const baseDeServicos = [
  {
    id: "01",
    duracao: "4H",
    titulo: "Lavagem Essencial",
    imagemUrl: "/ths-car-wash.png",
    precos: {
      popular: "R$ 120",
      suv: "R$ 160",
      caminhonete: "R$ 190",
    },
    beneficios: [
      { texto: "Pré Lavagem" },
      { texto: "Lavagem convencional Snow Foam" },
      { texto: "Lavagem dos pneus e caixa de roda" },
      { texto: "Revitalização de pneus" },
      { texto: "Aplicação de cera líquida (3 meses)" },
    ],
  },
  {
    id: "02",
    duracao: "7H",
    titulo: "Lavagem Detalhada",
    imagemUrl: "/ths-detailed-wash.png",
    precos: {
      popular: "R$ 270",
      suv: "R$ 350",
      caminhonete: "R$ 420",
    },
    beneficios: [
      { texto: "Pré Lavagem" },
      { texto: "Limpeza detalhada Snow Foam" },
      { texto: "Detalhamento dos pneus e caixa de roda" },
      { texto: "Descontaminação interna básica (painel e aspiração)" },
      { texto: "Revitalização de plásticos externos" },
      { texto: "Aplicação de selante de pintura (5 meses)" },
    ],
  },
  {
    id: "03",
    duracao: "6H",
    titulo: "Higienização Interna",
    imagemUrl: "/ths-car-interior.png",
    precos: {
      popular: "R$ 300",
      suv: "R$ 400 (7 lugares)",
      caminhonete: "R$ 400",
    },
    beneficios: [
      {
        texto:
          "Limpeza detalhada: couro, estofados, carpete, teto, cinto e porta-malas",
      },
      { texto: "Recondicionamento dos plásticos internos" },
      { texto: "Hidratação de couro" },
    ],
  },
  {
    id: "04",
    duracao: "2H",
    titulo: "Lavagem de motor",
    imagemUrl: "/ths-motor-clean.png",
    precos: {
      popular: "R$ 120",
      suv: "R$ 300",
      caminhonete: "R$ 300",
    },
    beneficios: [
      {
        texto:
          "Limpeza detalhada: couro, estofados, carpete, teto, cinto e porta-malas",
      },
      { texto: "Recondicionamento dos plásticos internos" },
      { texto: "Hidratação de couro" },
    ],
  },
];
const baseDeServicosEspecializados = [
  {
    id: "01",
    badge: "Corrige até 70% das imperfeições",
    duracao: "7H",
    titulo: "Polimento Comercial",
    imagemUrl: "/ths-polishing.png",
    precos: {
      popular: "R$ 500",
      suv: "R$ 650",
      caminhonete: "R$ 750",
    },
    beneficios: [
      { texto: "Ideal para preparação da venda do veículo" },
      { texto: "Lavagem e Descontaminação da pintura" },
      { texto: "Correção parcial do verniz" },
      { texto: "Aplicação de proteção (Cera)" },
    ],
  },
  {
    id: "02",
    badge: "Máximo resultado possível",
    duracao: "2 DIAS",
    titulo: "Polimento Técnico",
    imagemUrl: "/ths-tecnical-polishing.png",
    precos: {
      popular: "R$ 270",
      suv: "R$ 350",
      caminhonete: "R$ 420",
    },
    beneficios: [
      { texto: "Lavagem e Descontaminação da pintura" },
      { texto: "Correção completa do verniz" },
      { texto: "Aplicação de proteção (Selante)" },
    ],
  },
  {
    id: "03",
    badge: "Brilho de Show Room",
    duracao: "2 DIAS",
    titulo: "Higienização Interna",
    imagemUrl: "/ths-vitrification.png",
    precos: {
      popular: "R$ 1000",
      suv: "Consultar",
      caminhonete: "Consultar",
    },
    beneficios: [
      { texto: "Polimento técnico incluso" },
      { texto: "Proteção contra sujeiras, riscos e agentes externos" },
      { texto: "Intensifica o brilho e facilita a manutenção" },
    ],
  },
];

const pacotes = [
  {
    id: 1,
    titulo: "PACOTE BRONZE",
    corTitulo: "#CD7F32",
    duracao: "2 DIAS",
    parcelas: "5x",
    precos: {
      popular: "R$ 850",
      suv: "R$ 1100",
      caminhonete: "R$ 1380",
    },
    precosParcelados: {
      popular: "R$ 170",
      suv: "R$ 220",
      caminhonete: "R$ 276",
    },
    beneficios: [
      { texto: "Lavagem Essencial" },
      { texto: "Polimento Comercial" },
      { texto: "Higienização Interna" },
    ],
  },
  {
    id: 2,
    titulo: "PACOTE PRATA",
    corTitulo: "#C0C0C0", // Cor prata
    duracao: "3 DIAS",
    parcelas: "10x",
    precos: {
      popular: "R$ 1920",
      suv: "R$ 2700",
      caminhonete: "R$ 3380",
    },
    precosParcelados: {
      popular: "R$ 192",
      suv: "R$ 270",
      caminhonete: "R$ 338",
    },
    beneficios: [
      { texto: "Lavagem detalhada" },
      { texto: "Polimento espelhado" },
      { texto: "Vitrificação (3 anos)" },
      { texto: "Higienização interna" },
      { texto: "Revitalização de plásticos internos e externos" },
    ],
  },
  {
    id: 3,
    titulo: "PACOTE OURO",
    corTitulo: "#FFD700", // Cor ouro
    duracao: "4 DIAS",
    parcelas: "10x",
    precos: {
      popular: "R$ 4200",
      suv: "R$ 5750",
      caminhonete: "R$ 7150",
    },
    precosParcelados: {
      popular: "R$ 420",
      suv: "R$ 575",
      caminhonete: "R$ 715",
    },
    beneficios: [
      { texto: "Lavagem Detalhada" },
      { texto: "Polimento Técnico" },
      { texto: "Vitrificação (5 anos)" },
      { texto: "Revitalização de plásticos internos e externos" },
      { texto: "Higienização interna" },
      { texto: "Limpeza do motor detalhada" },
    ],
  },
];

const baseDeServicosMotos = [
  {
    id: "01",
    duracao: "3H",
    titulo: "Limpeza Premium N°1",
    imagemUrl: "/ths-motocycle-wash.png",
    precos: {
      popular: "A partir de R$ 80",
      suv: "A partir de R$ 80",
      caminhonete: "A partir de R$ 80",
    },
    beneficios: [
      { texto: "Limpeza técnica" },
      { texto: "Selante anti-derrapante" },
    ],
  },
  {
    id: "02",
    duracao: "5H",
    titulo: "Limpeza Premium N°2",
    imagemUrl: "/ths-premium-motocycle-wash.png",
    precos: {
      popular: "A partir de R$ 130",
      suv: "A partir de R$ 130",
      caminhonete: "A partir de R$ 130",
    },
    beneficios: [
      { texto: "Lavagem Premium Nº 1 inclusa" },
      { texto: "Revitalização de plásticos" },
      { texto: "Selante de pintura (5 meses)" },
      { texto: "Limpeza e lubrificação de corrente" },
    ],
  },
  {
    id: "03",
    duracao: "8H",
    titulo: "Polimento para Motos",
    imagemUrl: "/ths-motocycle-polishing.png",
    precos: {
      popular: "A partir de R$ 300",
      suv: "A partir de R$ 300",
      caminhonete: "A partir de R$ 300",
    },
    beneficios: [
      { texto: "Correção de verniz" },
      { texto: "Selagem de pintura (5 meses)" },
    ],
  },
];

const servicosPrincipais = computed(() => {
  return baseDeServicos.map((servico) => {
    return {
      ...servico,
      preco: servico.precos[veiculoSelecionado.value],
    };
  });
});

const servicosEspecializados = computed(() => {
  return baseDeServicosEspecializados.map((servico) => {
    return {
      ...servico,
      preco: servico.precos[veiculoSelecionado.value],
    };
  });
});

const servicosPacotes = computed(() => {
  return pacotes.map((servico) => {
    return {
      ...servico,
      preco: servico.precos[veiculoSelecionado.value],
    };
  });
});
const servicosMotos = computed(() => {
  return baseDeServicosMotos.map((servico) => {
    return {
      ...servico,
      preco: servico.precos[veiculoSelecionado.value],
    };
  });
});
</script>
