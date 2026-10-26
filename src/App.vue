<script setup>
// Dados estruturados do currículo do Marty McFly
const curriculo = {
  iniciais: 'MM',
  nome: 'Marty McFly',
  tituloProfissional: 'Consultor de Cronologia e Especialista em Performance Musical',
  resumo:
    'Jovem dinâmico, pontual (quando o capacitor de fluxo permite) e com vasta experiência em resolução de paradoxos temporais. Guitarrista talentoso com domínio de técnicas avançadas de shredding antes mesmo de serem inventadas. Experiente em lidar com figuras históricas, direção defensiva de veículos modificados e skate urbano. Nota: Não me chame de frangote.',
  experiencias: [
    {
      periodo: '1985 – Presente | The Pinheads',
      cargo: 'Guitarrista Principal',
      descricao:
        'Composição e performance de Rock \'n\' Roll. Responsável pela audição da "Batalha das Bandas" (mesmo sendo considerado "barulhento demais" por alguns juízes).'
    },
    {
      periodo: '1955 – Baile Encanto sob o Mar',
      cargo: 'Músico Substituto (Guitarra)',
      descricao:
        'Substituição emergencial do guitarrista Marvin Berry. Responsável pela introdução cultural do gênero Heavy Metal trinta anos antes do previsto.'
    },
    {
      periodo: '1885 – Consultoria de Segurança Hill Valley (Velho Oeste)',
      cargo: 'Assistente de Ferreiro',
      descricao:
        'Auxílio técnico em engenharia ferroviária improvisada e mediação de conflitos com a gangue de Buford "Cachorro Louco" Tannen.'
    },
    {
      periodo: '1985 – Indústrias Biffco',
      cargo: 'Sobrevivente Urbano',
      descricao:
        'Gestão de crises em ambientes distópicos e recuperação de artefatos esportivos (almanaques) para restauração da ordem cronológica.'
    }
  ],
  educacao: [
    {
      titulo: '1986 | Hill Valley High School',
      subtitulo: 'Ensino Médio Completo',
      descricao: 'Foco em Artes e Música'
    },
    {
      titulo: '1955 | Cultural Hill Valley',
      subtitulo: 'Intercâmbio',
      descricao:
        'Estudos intensivos sobre dinâmicas sociais da década de 50 e etiqueta de lanchonetes.'
    },
    {
      titulo: '1985 | Engenharia Aplicada',
      subtitulo: 'Workshop',
      descricao:
        'Treinamento prático em sistemas de 1.21 Gigawatts e mecânica de DeLorean (sob mentoria do Dr. Emmett Brown).'
    },
    {
      titulo: '2015 | Mobilidade Urbana Futurista',
      subtitulo: 'Treinamento',
      descricao:
        'Curso intensivo de pilotagem de Hoverboard em superfícies sólidas (atenção: pranchas não funcionam na água sem potência extra).'
    }
  ],
  contato: {
    endereco: 'Lyon Estates, Hill Valley, CA.',
    email: 'contato@delorean.com',
    telefone: '+55 (88) 9999 0000'
  },
  copyright: 'COPYRIGHT 2026 - TODOS OS DIREITOS RESERVADOS'
}
</script>

<template>
  <!-- Fundo externo da página -->
  <div class="min-h-screen py-10 px-4 font-sans bg-neutral-100 text-neutral-900">
    <!-- Folha do Currículo -->
    <main class="max-w-4xl mx-auto px-8 py-10 md:px-16 md:py-14 shadow-md bg-white">
      <!-- CABEÇALHO: Quadrado Amarelo MM + Nome/Cargo -->
      <header class="flex items-center gap-6 mb-10">
        <!-- Quadrado Amarelo MM -->
        <div class="w-20 h-20 bg-[#ead428] text-black flex items-center justify-center font-bold text-4xl tracking-wider shrink-0">
          {{ curriculo.iniciais }}
        </div>

        <!-- Nome e Subtítulo em fonte monoespaçada -->
        <div>
          <h1 class="font-mono text-xl font-bold text-neutral-900 mb-1">
            {{ curriculo.nome }}
          </h1>
          <p class="font-mono text-xs sm:text-sm text-neutral-700">
            {{ curriculo.tituloProfissional }}
          </p>
        </div>
      </header>

      <!-- GRID PRINCIPAL DE 2 COLUNAS -->
      <div class="grid grid-cols-1 md:grid-cols-[1.75fr_1fr]">
        <!-- COLUNA ESQUERDA: Resumo + Experiências + Rodapé -->
        <div class="md:pr-11 flex flex-col justify-between">
          <div>
            <!-- Parágrafo de Resumo -->
            <p class="text-[13.5px] leading-relaxed text-neutral-800 mb-9">
              {{ curriculo.resumo }}
            </p>

            <!-- Seção de Experiências Profissionais -->
            <section>
              <h2 class="text-[11px] font-bold tracking-[0.2em] uppercase text-neutral-400 mb-6">
                EXPERIÊNCIAS PROFISSIONAIS
              </h2>

              <article
                v-for="(exp, index) in curriculo.experiencias"
                :key="index"
                class="mb-7"
              >
                <h3 class="text-[14px] font-bold text-neutral-900 mb-1">
                  {{ exp.periodo }}
                </h3>
                <p class="font-mono text-[13px] font-bold text-neutral-400 mb-2">
                  {{ exp.cargo }}
                </p>
                <p class="text-[13.5px] leading-relaxed text-neutral-700">
                  {{ exp.descricao }}
                </p>
              </article>
            </section>
          </div>

          <!-- Rodapé Copyright -->
          <footer class="border-t border-neutral-100 pt-7 mt-4 text-[10.5px] font-bold tracking-[0.18em] uppercase text-neutral-400">
            {{ curriculo.copyright }}
          </footer>
        </div>

        <!-- COLUNA DIREITA: Educação + Contato -->
        <aside class="md:pl-9 md:border-l border-t md:border-t-0 border-neutral-100 pt-8 md:pt-0 mt-8 md:mt-0 flex flex-col justify-between">
          <!-- Seção de Educação -->
          <section>
            <h2 class="text-[11px] font-bold tracking-[0.2em] uppercase text-neutral-400 mb-6">
              EDUCAÇÃO
            </h2>

            <article
              v-for="(edu, index) in curriculo.educacao"
              :key="index"
              class="mb-7"
            >
              <h3 class="text-[14px] font-bold text-neutral-900 mb-1">
                {{ edu.titulo }}
              </h3>
              <p class="font-mono text-[13px] font-bold text-neutral-400 mb-2">
                {{ edu.subtitulo }}
              </p>
              <p class="text-[13.5px] leading-relaxed text-neutral-700">
                {{ edu.descricao }}
              </p>
            </article>
          </section>

          <!-- Seção de Contato -->
          <section class="border-t border-neutral-100 pt-7 mt-4">
            <h2 class="text-[11px] font-bold tracking-[0.2em] uppercase text-neutral-400 mb-5">
              CONTATO
            </h2>

            <ul class="text-[12px] space-y-2.5 text-neutral-700">
              <li>
                <strong class="font-bold text-neutral-900">ENDEREÇO:</strong>
                {{ curriculo.contato.endereco }}
              </li>
              <li>
                <strong class="font-bold text-neutral-900">E-MAIL:</strong>
                {{ curriculo.contato.email }}
              </li>
              <li>
                <strong class="font-bold text-neutral-900">TELEFONE:</strong>
                {{ curriculo.contato.telefone }}
              </li>
            </ul>
          </section>
        </aside>
      </div>
    </main>
  </div>
</template>
