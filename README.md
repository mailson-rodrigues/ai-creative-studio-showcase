# AI Creative Studio (vitrine)

Plataforma em desenvolvimento para **criar livros ilustrados, jogos e produtos digitais** a partir de histórias, desenhos e ideias, com **IA de vários provedores** e **aprovação humana em cada etapa**. A autoria original é sempre preservada.

> Este repositório é uma **vitrine**. O código do produto é privado e **não está aqui**. Aqui estão a visão, a arquitetura e as garantias de engenharia. "AI Creative Studio" é um nome provisório, sem marca registrada.

## O que há aqui

| Caminho | Conteúdo |
|---|---|
| [`docs/01-arquitetura.md`](docs/01-arquitetura.md) | Monólito modular, fronteiras entre módulos, fluxo de geração com IA |
| [`docs/02-integridade-e-seguranca.md`](docs/02-integridade-e-seguranca.md) | Ativos aprovados imutáveis no banco, auditoria encadeada, aprovação só por humanos |
| [`docs/04-livros-e-jogos.md`](docs/04-livros-e-jogos.md) | Páginas em camadas, PDF digital e de impressão, jogo digital e kit imprimível |
| [`docs/05-loja-e-conformidade.md`](docs/05-loja-e-conformidade.md) | Pagamento com assinatura verificada, entrega temporária, aceite com prova e arrependimento |
| [`docs/06-homologacao.md`](docs/06-homologacao.md) | Os 20 critérios do MVP: o que está atendido, o que está parcial e por quê |
| [`docs/03-qualidade-e-evidencias.md`](docs/03-qualidade-e-evidencias.md) | Estratégia de testes, o que já foi verificado e o que ainda não foi |

## Princípios

* **Nada aprovado é sobrescrito:** uma ilustração, texto ou capa aprovados só mudam por **nova versão**. A regra vale no banco de dados, não só na aplicação.
* **Humano decide:** agentes de IA propõem; apenas pessoas autorizadas aprovam ou publicam.
* **Independência de fornecedor:** a aplicação pede *capacidades* (gerar imagem, editar imagem, analisar), e adaptadores falam com cada provedor.
* **Custo sob controle:** estimativa antes, teto por projeto e aprovação acima do limite.
* **Texto separado da arte:** páginas são camadas; corrigir um texto nunca toca nas imagens.
* **Proteção de crianças:** conteúdo de menores só é publicado com consentimento registrado.

## Estado

Em desenvolvimento, em fases, cada uma com evidência de teste. Implementados e testados: identidade (MFA, bloqueio), auditoria encadeada, ativos imutáveis, API REST, camada de IA com adaptadores **simulados**, memória do projeto, livros com páginas em camadas e PDF, jogo digital, kit de jogo imprimível, e a loja (serviços e API HTTP). A fase de homologação foi executada em ambiente local.

**Ainda não existe:** conexão com provedores reais de IA, interface do usuário, conexão real com o meio de pagamento, textos legais publicados. Veja os limites de cada área nos documentos acima.
