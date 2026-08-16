# Campo de Treino — Muay Thai & Força

PWA de treino pessoal: agenda semanal, musculação voltada a potência, muay thai em casa (saco e aparador), mobilidade e acompanhamento corporal.

**Acesso:** https://duarttes.github.io/muaythai/

## Conteúdo

| Aba | O que tem |
|---|---|
| Agenda | Divisão da semana — muay thai seg/qua/sex, força ter/qui/sáb, domingo recuperação |
| Musculação | 3 dias (inferiores, superiores, full body) focados em explosão, não hipertrofia |
| Muay Thai em Casa | 3 sessões: técnica no saco, potência/condicionamento, aparador com parceiro |
| Mobilidade | Bloco dinâmico pré-treino e estático pós-treino |
| Fortalecimento | Prehab — pescoço, core, tornozelo, equilíbrio e pegada |
| Corpo & Dieta | Protocolo de pesagem por bioimpedância e metas de nutrição |

Cada exercício tem um botão **Ver** que abre a busca da execução no YouTube.

## Stack

HTML/CSS/JS puro, sem build. Todo o conteúdo vive em arrays no `<script>` do `index.html` — para editar um treino, mude o array correspondente (`musc`, `casa`, `mob`, `forte`).

## PWA

`manifest.json` + `sw.js` permitem instalar no celular e usar offline. O service worker é network-first para o HTML (atualizações chegam sozinhas) e cache-first para ícones e fontes.

Ao alterar arquivos do `CORE`, suba o número em `const CACHE = 'treino-vN'` no `sw.js` para invalidar o cache antigo.

## Deploy

GitHub Pages a partir do branch `main`, raiz do repositório. Push no `main` publica.
