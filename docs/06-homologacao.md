# Homologação

Executada em ambiente de desenvolvimento local. **Não é produção.** A IA e o pagamento são simulados. Um critério só conta como atendido se existe teste ou registro arquivado.

## Os 20 critérios do MVP
Resultado: **12 atendidos e 8 parciais**.

| # | Critério | Situação | O que falta |
|---|---|---|---|
| 1 | Criar projetos | Parcial | Interface gráfica |
| 2 | Importar histórias | Parcial | Importador de PDF e DOCX |
| 3 | Registrar personagens | Atendido | — |
| 4 | Preservar versões aprovadas | Atendido | — |
| 5 | Gerar imagens por API | Parcial | Nenhuma geração real: faltam chaves com faturamento |
| 6 | Editar textos sem alterar imagens | Atendido | — |
| 7 | Criar livros ilustrados | Parcial | O livro real do piloto ainda não foi importado |
| 8 | Exportar PDF | Atendido, com ressalvas | Apenas RGB; nenhuma gráfica validou |
| 9 | Jogo de memória digital | Parcial | Falta teste automatizado em navegador |
| 10 | Memória imprimível | Atendido (arquivos) | Nada foi impresso nem cortado |
| 11 | Verificações de qualidade | Atendido | Sem corretor ortográfico |
| 12 | Aprovar versões | Atendido | — |
| 13 | Publicar na loja | Parcial | Sem vitrine pública nem interface |
| 14 | Simular pagamentos | Parcial | O ambiente de testes real do meio de pagamento nunca foi chamado |
| 15 | Processar webhooks | Atendido (lógica) | Formato conferido pela documentação, não por um evento real |
| 16 | Liberar downloads | Atendido | — |
| 17 | Consultar histórico | Atendido (API) | Sem tela |
| 18 | Restaurar versões | Atendido | — |
| 19 | Medir consumo de APIs | Parcial | Sem painel de custos |
| 20 | Backups testados | Atendido (local) | Destino externo e rotina agendada |

Há ainda um **teste ponta a ponta** que percorre projeto, história, personagem, ilustração simulada, aprovação, livro, PDFs, jogo digital, jogo físico, qualidade, loja, compra simulada, pagamento simulado, download e auditoria.

## Segurança
* Análise estática com regras de segurança e auditoria de dependências: sem avisos.
* Verificação de configuração de produção do framework: 2 avisos, ambos dependentes de decisão de domínio.
* Webhook com falha fechada, assinatura, janela de tempo e conferência de valor; download com link temporário; isolamento entre organizações e entre clientes.
* **Não feito:** teste de intrusão, varredura dinâmica, revisão de ameaças por terceiros, antivírus de upload.

## Desempenho
Teste de fumaça com um usuário e dados sintéticos pequenos: exportar um livro de 16 páginas leva cerca de 1,5 segundo; 100 consultas à API, menos de 1 segundo. Isso **não é teste de carga** nem promessa de capacidade.

## Recuperação
Backup restaurado em banco limpo: registros de auditoria e versões iguais aos da origem, arquivos sem divergência de hash e cadeia de auditoria íntegra.

## O que impede declarar o produto pronto
Nenhuma IA, pagamento ou impressão reais foram executados; não há interface gráfica; os textos legais ainda não foram publicados nem revisados por advogado; o ambiente de produção não existe.
