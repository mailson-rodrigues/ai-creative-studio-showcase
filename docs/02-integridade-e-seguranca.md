# Integridade e segurança

## Ativos aprovados são imutáveis, no banco
Cada arquivo tem versões. Quando uma versão é **aprovada** ou **publicada**:
* o conteúdo, o hash, a origem e o histórico ficam congelados;
* o banco de dados recusa `UPDATE`, `DELETE` e `TRUNCATE` sobre ela, **inclusive por SQL direto**;
* o estado só avança (aprovada → publicada → arquivada), nunca volta para rascunho;
* "restaurar" cria uma **nova versão** a partir da antiga, sem apagar nada.

A proteção existe na aplicação **e** no banco: se houver um bug no código, o banco ainda impede a alteração.

## Auditoria que denuncia adulteração
O registro de auditoria é *append-only* (o banco bloqueia alterações e remoções) e cada linha guarda o hash da anterior. Se alguém com acesso privilegiado desligasse a proteção e alterasse uma linha, a verificação da cadeia aponta exatamente onde.

## Só humanos aprovam
Contas de agentes de IA existem, mas **nunca** aprovam nem publicam. Aprovar exige papel com permissão, mesma organização e **motivo registrado**.

## Uploads
O tipo do arquivo vem do **conteúdo real**, não do nome nem do cabeçalho enviado. Há limites de tamanho e de pixels, e arquivos truncados, formatos não permitidos (como SVG com script) e executáveis disfarçados são rejeitados. Cada leitura confere o hash; arquivo adulterado ou ausente é detectado.

## Proteção de crianças
Material que contenha dados de menores é marcado, e a **publicação é bloqueada** sem consentimento registrado do responsável.

## Dependências
Versões fixadas em arquivo de travamento e auditadas por ferramenta de vulnerabilidades. A primeira auditoria encontrou falhas conhecidas na biblioteca de imagens, que processa arquivos não confiáveis; foi atualizada na mesma fase e a auditoria passou a não encontrar nenhuma.

## Limites conhecidos
* A proteção por gatilho do banco não vale contra um superusuário do banco. Por isso existe o hash encadeado, e em produção a aplicação usará um papel sem privilégio de superusuário.
* Ainda não implementados: autenticação multifator, bloqueio por tentativas, limitação de taxa e a API HTTP.
