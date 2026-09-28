# Validação das afirmações — Muse × OpenMuse

Checagem feita em **28/09/2026**. Fonte analisada: vídeo comparativo no YouTube (em alemão),
<https://www.youtube.com/watch?v=cDTkWh_W-4k>. Cada afirmação foi conferida na newsroom da Meta,
na imprensa e no repositório do OpenMuse, lido pela API do GitHub (`gh api repos/CopilotKit/openmuse`).

Legenda: ✅ confirmado · ⚠️ parcial, desatualizado ou erro de transcrição · ❌ divergente · ❔ não verificado

## Meta Muse

| # | Afirmação do vídeo | Status | Dado real | Fonte |
|---|---|---|---|---|
| 1 | Lançado em 8/set/2026 como “primeiro agente pessoal de IA para todos” | ✅ | “The world's first personal AI agent built for everyone” | [Meta Newsroom](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/) |
| 2 | Computador dedicado na nuvem (“Muse Secure Machine”), navegador visível, usuário assume | ✅ | Nome oficial: **Muse Secure VM**; Chromium virtualizado, visível e com controle manual | [Meta AI](https://research.meta.ai/blog/security-and-safety-for-ai-agents-our-approach-with-muse), [TechCrunch](https://techcrunch.com/2026/09/08/meta-debuts-its-muse-ai-agent-will-consumers-trust-it/) |
| 3 | Compras, ingressos de cinema, aula de tênis, autorização de passeio escolar | ✅ | Mesmos exemplos no anúncio | [Meta Newsroom](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/) |
| 4 | Nome, avatar, tom; memória; “esqueça isso” | ✅ | Personalização e memória com controle de esquecimento | [Meta Newsroom](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/) |
| 5 | Dados fora dos anúncios; futura “Confidential Machine” com chave do usuário | ✅ | **Muse Confidential VM** prometida para o fim do ano (promessa, não recurso disponível) | [Meta AI](https://research.meta.ai/blog/security-and-safety-for-ai-agents-our-approach-with-muse) |
| 6 | Grátis + US$ 20 e US$ 100/mês; EUA, iOS, Android e web; óculos em breve | ✅ | Idem; web em muse.ai | [Axios](https://www.axios.com/2026/09/08/meta-debuts-muse-personal-ai-agent) |
| 7 | Connect: voz, voz por descrição, avatar Jolly, óculos por palavra de ativação, treino, refeições, compras | ✅ | Connect em **23/set/2026** | [TechCrunch](https://techcrunch.com/2026/09/23/everything-new-coming-to-metas-ai-agent-muse/), [Meta](https://about.fb.com/news/2026/09/the-biggest-news-from-connect-2026/) |
| 8 | Acordo de US$ 18 bi com estados dos EUA, ~2 semanas antes | ⚠️ | **US$ 18 bilhões**, 29 estados, 26/ago/2026. Num trecho o vídeo diz “18 milhões” | [TechCrunch](https://techcrunch.com/2026/08/26/meta-settles-for-18-billion-in-lawsuit-brought-by-29-states-over-social-media-harms-to-children/), [Washington Post](https://www.washingtonpost.com/technology/2026/08/26/meta-pay-up-18b-settle-lawsuit-alleging-social-media-harm-children/) |
| 9 | Pede acesso a e-mail, calendário, pagamentos e saúde | ❔ | E-mail e calendário aparecem na cobertura; não achamos fonte primária listando saúde e pagamentos como permissões | — |

## OpenMuse (CopilotKit)

| # | Afirmação do vídeo | Status | Dado real | Fonte |
|---|---|---|---|---|
| 10 | MIT; 2.100★, 230 forks, 22 branches | ⚠️ | MIT confirmado. Em 28/09: **2.765★, 351 forks, 22 branches, 54 commits**; criado em 15/09, último push em 26/09 | [CopilotKit/openmuse](https://github.com/CopilotKit/openmuse) |
| 11 | Inspirado no Meta Muse, sucessor do “Open Bot” | ✅ | [CopilotKit/OpenBot](https://github.com/CopilotKit/openbot); adaptador presente, mas desativado | README |
| 12 | Expo/RN, Hono + runtime CopilotKit, eventos, worker com leases, Playwright, Docker sem root, 30 s/comando | ✅ | Bate com o README (eventos AG-UI, leases SQL) | README |
| 12b | Banco “Pika Light” | ⚠️ | Transcrição de **PGlite** (`@electric-sql/pglite`); opção de PostgreSQL | README |
| 13 | Chat, fila, atividade, Ideas, metas, PDF, finanças só leitura, Gmail/Calendar, perfil | ✅ | A tabela de recursos bate item a item | README |
| 14 | Alfa; roadmap com saúde, banco, voz e compras autônomas | ✅ | “Alpha, for self-hosting and building on”; roadmap inclui ainda ferramentas geradas e push no aparelho | README, ROADMAP.md |
| 15 | Node 24, pnpm 11.19.0, “4 comandos” | ⚠️ | pnpm exato. O README pede Node 24 LTS (`engines` aceita ≥22). O quickstart tem **6 comandos** + `pnpm dev:web` | README, package.json |
| 16 | Básico sem nenhum serviço externo | ❌ | Dispensa modelo, Google e Docker, **mas exige `CPK_INTELLIGENCE_API_KEY` em todo modo**. O CopilotKit Intelligence é um serviço separado, fora da licença MIT | README (“Rich Threads”) |

## Erros notáveis do vídeo

- **“18 milhões”**: o valor correto é US$ 18 **bilhões**. O próprio vídeo acerta em outros trechos.
- **“Pika Light”** = PGlite.
- **“Open News”** (em dois trechos) = OpenMuse; é erro de transcrição/dublagem.
- **“Secure Machine” / “Confidential Machine”**: os nomes oficiais são *Secure VM* / *Confidential VM*.
- **Dependência omitida**: o vídeo apresenta o OpenMuse como totalmente independente, mas a persistência de conversas depende do CopilotKit Intelligence.
- **Números do repositório**: defasados, porque o repositório cresceu depois da gravação.
