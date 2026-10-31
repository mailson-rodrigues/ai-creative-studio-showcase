# Livros e jogos

## Livros em camadas
Cada página tem camadas separadas de **arte** e **texto**. Corrigir um texto nunca toca na imagem aprovada. Páginas têm versões que só acrescentam: restaurar cria uma versão nova.

## PDF
Dois perfis, gerados de forma determinística (mesma entrada, mesmo arquivo):
* **Digital:** tamanho de página, fontes embutidas, texto selecionável.
* **Impressão:** sangria de 3 mm e área de marcas, com caixas de corte e de sangria declaradas no PDF.

Verificações automáticas sobre o arquivo gerado: número de páginas, fontes embutidas, texto extraível, resolução efetiva das imagens (reprova abaixo de 200 dpi, avisa abaixo de 300) e uso de cor. O PDF é **RGB**; não há CMYK nem PDF/X, e isso é avisado em cada exportação.

## Jogo digital
Jogo da memória em **um único arquivo HTML**, que abre sem servidor. Regras e embaralhamento existem em Python e em JavaScript e são comparados por teste (mesma semente, mesmo resultado). O arquivo carrega uma política de segurança com *hash* do script, e os dados entram escapados e só como texto. Cartas só vêm de imagens **aprovadas**; uma prévia com imagem não aprovada fica registrada como tal.

## Jogo físico (memória imprimível)
O kit sai de imagens aprovadas e inclui:
* **PDF de impressão** com frente e verso por folha, legendas em texto, sangria e marcas de corte nas margens; o verso é espelhado para a virada pela borda longa ou curta;
* **arquivo de corte em SVG** (milímetros);
* **ficha técnica e manual**, com custos apenas dos valores informados pelo usuário.

O espaço entre cartas é o dobro da sangria, para que a sangria de uma carta não alcance o corte da vizinha. O texto do produto **não pode** declarar segurança ou certificação; a ficha sempre diz que o arquivo não é produto certificado e que nenhum ensaio foi feito.

## Limites
Nada foi impresso nem cortado em papel; cor e alinhamento reais dependem da impressora e da gráfica. Só o jogo da memória está implementado. A avaliação regulatória de brinquedos no Brasil não foi feita.
