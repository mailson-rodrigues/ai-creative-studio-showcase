# Qualidade e evidências

Regra do projeto: **nada é declarado como testado sem log ou relatório.**

## Verificado (executado)
| Verificação | Resultado |
|---|---|
| Testes automatizados contra PostgreSQL real | 214 passando (acesso, ativos imutáveis, IA simulada, livros, jogos, kit imprimível, loja e um fluxo ponta a ponta) |
| Análise estática (lint) | sem avisos |
| Auditoria de vulnerabilidades das dependências | nenhuma conhecida (após atualização) |
| Entradas malformadas na API | corpo que não é objeto JSON, identificadores inválidos e listas erradas respondem 4xx, nunca 500 (um erro real foi encontrado e corrigido) |
| Fronteiras entre módulos | contratos passam e **quebram** quando violados (verificado) |
| Exercício de restauração de backup | backup → banco limpo → conferência de hashes, contagens e cadeia de auditoria: sem divergência |
| Checagem de configuração de produção do framework | restam apenas 2 avisos dependentes de decisão de domínio |

Os testes de imutabilidade tentam burlar a regra por SQL direto, remoção, truncamento e retrocesso de estado; todas as tentativas são recusadas.

## Ainda não verificado
* Integração real com provedores de IA (depende de credenciais com faturamento).
* Interface do usuário.
* Pagamentos: a lógica de assinatura, idempotência e entrega é testada com um provedor **simulado**; nenhuma chamada real ao meio de pagamento foi feita.
* Impressão física: nenhum kit foi impresso ou cortado em papel.
* Qualidade semântica da memória do projeto (usa vetores simulados nos testes).
* Revisão jurídica de direitos de autor sobre imagens geradas por IA.

## Como as verificações são validadas
Em pontos críticos usamos **teste de mutação manual**: quebramos a regra de propósito (por exemplo, a conferência da assinatura do webhook, o valor do pagamento ou o espaço entre cartas na folha de impressão) e confirmamos que os testes falham. Só depois a regra é restaurada.

## Observação sobre o piloto
O projeto é validado com uma obra infantil real, cujos arquivos e dados **não são publicados** aqui.
