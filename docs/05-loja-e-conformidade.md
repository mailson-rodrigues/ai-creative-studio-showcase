# Loja e conformidade

Venda de **produtos digitais** (um arquivo por produto). Só versões **aprovadas ou publicadas** podem ser vendidas, e só pessoas autorizadas as colocam à venda; agentes de IA não.

## Pagamento
O desenho segue a documentação oficial do meio de pagamento (Mercado Pago, Checkout Pro):
* a notificação é aceita só com **assinatura válida** (HMAC-SHA256 sobre os campos documentados, comparação em tempo constante, janela de tempo contra repetição). Sem o segredo configurado, nada é aceito;
* o estado do pagamento é **consultado ao provedor**; o corpo da notificação não é confiável sozinho;
* valor ou moeda divergentes **não liberam** o pedido;
* repetir a mesma notificação não tem efeito (idempotência);
* o preço fica congelado no pedido.

## Entrega
Link temporário com validade curta e número máximo de usos; o código do link não é guardado (só seu *hash*). Reembolso ou arrependimento encerram o acesso, e o arquivo é conferido por *hash* a cada download.

## Conformidade (LGPD e Código de Defesa do Consumidor)
Implementado a partir de um parecer jurídico:
* **aceite ativo** dos Termos e da Política de Privacidade (nunca pré-marcado), com registro imutável de usuário, IP, versão e horário em UTC;
* **versões imutáveis** dos textos; texto com campos não preenchidos é recusado;
* **resumo de compra** antes do botão final;
* **arrependimento em 7 dias**, com protocolo e comprovante; o acesso é revogado na hora;
* o pagamento ocorre no meio de pagamento, sem dados de cartão no sistema.

## Limites
* **Nenhuma conexão real** com o meio de pagamento foi feita; a lógica foi testada com um provedor simulado.
* Os textos legais **ainda não foram publicados** e dependem de revisão jurídica.
* Sem interface, e-mail de confirmação, estorno automático ou nota fiscal.
