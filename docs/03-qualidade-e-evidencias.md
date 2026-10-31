# Qualidade e evidências

Regra do projeto: **nada é declarado como testado sem log ou relatório.**

## Verificado (executado)
| Verificação | Resultado |
|---|---|
| Testes automatizados contra PostgreSQL real | 36 passando |
| Análise estática (lint) | sem avisos |
| Auditoria de vulnerabilidades das dependências | nenhuma conhecida (após atualização) |
| Fronteiras entre módulos | contratos passam e **quebram** quando violados (verificado) |
| Exercício de restauração de backup | backup → banco limpo → conferência de hashes, contagens e cadeia de auditoria: sem divergência |
| Checagem de configuração de produção do framework | restam apenas 2 avisos dependentes de decisão de domínio |

Os testes de imutabilidade tentam burlar a regra por SQL direto, remoção, truncamento e retrocesso de estado; todas as tentativas são recusadas.

## Ainda não verificado
* Integração real com provedores de IA (depende de credenciais com faturamento).
* Autenticação multifator, API HTTP, interface e loja.
* Pagamentos: nenhum fluxo implementado.
* Revisão jurídica de direitos de autor sobre imagens geradas por IA.

## Observação sobre o piloto
O projeto é validado com uma obra infantil real, cujos arquivos e dados **não são publicados** aqui.
