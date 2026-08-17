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

Cada exercício tem um botão **Ver** que abre o vídeo da execução em um player embutido no próprio card, sem sair do site.

## Stack

HTML/CSS/JS puro, sem build. Todo o conteúdo vive em arrays no `<script>` do `index.html` — para editar um treino, mude o array correspondente (`musc`, `casa`, `mob`, `forte`).

## Vídeos

O objeto `videos` mapeia nome do exercício → `{id, channel, title}`. Os 47 IDs foram verificados: o vídeo existe e tem `playableInEmbed: true` (permite ser embutido). O player usa `youtube-nocookie.com` e só é criado ao clicar em **Ver** — fechar o card remove o iframe, o que interrompe a reprodução.

Exercício sem entrada no mapa cai automaticamente no link de busca do YouTube, então dá pra adicionar exercícios sem quebrar nada.

Para trocar um vídeo, edite o `id` correspondente. Se um vídeo sair do ar ou passar a bloquear embed, o card mostra o erro do player do YouTube — nesse caso o link "Abrir no YouTube" no rodapé do player continua funcionando.

## PWA

`manifest.json` + `sw.js` permitem instalar no celular e usar offline. O service worker é network-first para o HTML (atualizações chegam sozinhas) e cache-first para ícones e fontes.

Ao alterar arquivos do `CORE`, suba o número em `const CACHE = 'treino-vN'` no `sw.js` para invalidar o cache antigo.

## Deploy

GitHub Pages a partir do branch `main`, raiz do repositório. Push no `main` publica.
