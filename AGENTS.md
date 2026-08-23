## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

## Estrutura da Landing Page

A home (`src/pages/index.astro`) é composta por seções ("dobras"), cada uma um componente em `src/components/`:

| Dobra | Componente | Fundo |
|---|---|---|
| 1. Hero | `Hero.astro` | navy `#182338` |
| "Um laudo sem suporte..." (risco) | `Problem.astro` | quase-preto `#080d18` |
| 2. Nossos Serviços + Prova Social | `Services.astro` | cream `#eef4ed` |
| 3. Como Funciona | `Processo.astro` | navy `#111928` (`var(--primary)`) |
| 4. Atendimento Individualizado | `Audience.astro` (usa `Forms.astro`) | azul `#162947` |
| 5. Assistente Técnica | `Founder.astro` (bloco `founder-grid`) | cream `#eef4ed` |
| 6. O que nos diferencia | `Founder.astro` (bloco `founder-differentials`, mesmo arquivo) | cream `#eef4ed` |
| 7. Para Quem É (funde "Sobre a Plexus") | `Autorithy.astro` | navy claro `#182338` (`var(--gray-light)`) |
| 8. FAQ | `FAQ.astro` | cream `#eef4ed` |
| 9. CTA Final (Têmis) | `CtaFinal.astro` | imagem `fundoCtaFinal.png` |

Todos os estilos vivem em `src/styles/global.css` (sem framework CSS/JS de UI). Tokens principais: `--primary #111928`, `--secondary #1f2d47`, `--accent #f7d7b6` (peach, cor de destaque), `--gray-light #182338`, cream `#EEF4ED`. Um bloco perto do fim do arquivo, com o comentário `RENASCIMENTO — BACKGROUNDS & INTERATIVIDADE`, usa `!important` e sobrescreve as cores-base de várias dobras — é ele que define a cor final, não a regra do topo do arquivo. Novos overrides de cor devem ir nesse bloco (ou em outro com `!important` equivalente) para vencer a cascata.

Há um subagente dedicado a este projeto em `.claude/agents/plexus-landing.md` com mais detalhes de padrões reutilizáveis.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Using React, Vue, Svelte, or other framework components](https://docs.astro.build/en/guides/framework-components/)
- [Adding or managing content](https://docs.astro.build/en/guides/content-collections/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
- [Supporting multiple languages](https://docs.astro.build/en/guides/internationalization/)
