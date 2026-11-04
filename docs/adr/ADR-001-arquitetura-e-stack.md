# ADR-001 — Arquitetura e stack tecnológica

- **Situação:** aceita
- **Data:** 2026-11-04
- **Participantes:** Equipe 10

## Contexto

O projeto Connexa precisa de uma arquitetura e de uma stack tecnológica padronizadas para orientar o desenvolvimento durante as sprints. A equipe decidiu manter as tecnologias e diretrizes já documentadas no README.md.

## Decisão

A equipe decidiu adotar integralmente a arquitetura e a stack descritas no README.md, mantendo o backend como monólito modular com vertical slices e o frontend como uma SPA (Single Page Application).

A stack definida é:

- **Backend:** Node.js 24, TypeScript, NestJS 12 e Prisma 7 com Prisma Migrate.
- **Banco de dados:** PostgreSQL 17.
- **Dependências do backend:** @nestjs/event-emitter, @nestjs/swagger e class-validator.
- **Frontend:** React 19, TypeScript, Vite e React Router.
- **Gerenciamento de dados e formulários:** TanStack Query, React Hook Form e Zod.
- **Testes:** Vitest, Supertest e Testing Library.
- **Arquitetura e qualidade:** eslint-plugin-boundaries e testes de arquitetura.
- **Ambiente de desenvolvimento:** GitHub Codespaces (Dev Container) ou ambiente local com Docker.
- **Integração contínua:** GitHub Actions.

No backend, os módulos serão organizados respeitando suas fronteiras e a responsabilidade sobre os próprios dados. A comunicação entre módulos poderá utilizar eventos.

No frontend, as funcionalidades serão organizadas por features. A autenticação de estudantes será simulada durante a Sprint 1, conforme definido no README.

## Alternativas consideradas

| Alternativa | Por que não foi escolhida |
|---|---|
| Alterar a arquitetura ou a stack definida no README | A equipe decidiu manter a padronização já estabelecida para o projeto. |
| Adotar uma arquitetura diferente da documentada | A equipe optou por seguir o modelo arquitetural definido no README. |

## Consequências

- **Positivas:** padronização do desenvolvimento, organização das responsabilidades, consistência entre os integrantes e facilidade de manutenção.
- **Negativas:** a equipe deverá respeitar as tecnologias e os padrões escolhidos, o que limita mudanças de stack sem uma nova decisão arquitetural.
- **Como verificar:** revisar os arquivos de dependências, executar os testes e verificações de arquitetura e acompanhar os checks de CI do GitHub Actions.
