# AI Creative Studio (vitrine)

Plataforma em desenvolvimento para **criar livros ilustrados, jogos e produtos digitais** a partir de histórias, desenhos e ideias, com **IA de vários provedores** e **aprovação humana em cada etapa**. A autoria original é sempre preservada.

> Este repositório é uma **vitrine**. O código do produto é privado e **não está aqui**. Aqui estão a visão, a arquitetura e as garantias de engenharia. "AI Creative Studio" é um nome provisório, sem marca registrada.

## O que há aqui

| Caminho | Conteúdo |
|---|---|
| [`docs/01-arquitetura.md`](docs/01-arquitetura.md) | Monólito modular, fronteiras entre módulos, fluxo de geração com IA |
| [`docs/02-integridade-e-seguranca.md`](docs/02-integridade-e-seguranca.md) | Ativos aprovados imutáveis no banco, auditoria encadeada, aprovação só por humanos |
| [`docs/03-qualidade-e-evidencias.md`](docs/03-qualidade-e-evidencias.md) | Estratégia de testes, o que já foi verificado e o que ainda não foi |

## Princípios

* **Nada aprovado é sobrescrito:** uma ilustração, texto ou capa aprovados só mudam por **nova versão**. A regra vale no banco de dados, não só na aplicação.
* **Humano decide:** agentes de IA propõem; apenas pessoas autorizadas aprovam ou publicam.
* **Independência de fornecedor:** a aplicação pede *capacidades* (gerar imagem, editar imagem, analisar), e adaptadores falam com cada provedor.
* **Custo sob controle:** estimativa antes, teto por projeto e aprovação acima do limite.
* **Texto separado da arte:** páginas são camadas; corrigir um texto nunca toca nas imagens.
* **Proteção de crianças:** conteúdo de menores só é publicado com consentimento registrado.

## Estado

Em desenvolvimento. Núcleo de identidade, auditoria, projetos e ativos implementado e testado; AI Gateway, editor de livros, jogos e loja são as próximas fases.
