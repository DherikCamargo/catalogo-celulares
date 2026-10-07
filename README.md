# Catálogo de Celulares

Catálogo interativo de celulares, relógios e tablets, publicado no GitHub Pages:
https://dherikcamargo.github.io/catalogo-celulares/

Tudo fica em um único arquivo, `index.html` (HTML, CSS e JavaScript, sem build). As fotos ficam em `img/`.

## O que o catálogo faz

- Busca por modelo, memória, marca ou cor, e filtros por marca.
- Cada produto mostra preço no Pix, parcelamento no cartão, cores, memória e botão de WhatsApp.
- Janela com as parcelas de 1x a 12x, que fecha pelo X, clicando fora ou com `Esc`.
- Pedido com vários itens, enviado pelo WhatsApp.

## Regras do negócio

- **WhatsApp de atendimento:** constante `WHATSAPP` no `index.html`.
- **Preço Pix:** é o preço final de venda. Fica no 5º campo de cada linha do array `raw`.
- **Cartão em até 12x:** as taxas da InfinitePay são repassadas ao comprador. A constante `FACTORS` guarda o multiplicador de cada parcela, tirado de uma simulação real da InfinitePay (cliente paga R$ 3.131,53 em 1x ... R$ 3.599,72 em 12x para o vendedor receber R$ 3.000).
- **Nunca coloque custo de fornecedor ou margem de lucro no código nem nas mensagens de commit.** O repositório é público.

## Produtos e fotos

Cada linha do array `raw` é `[marca, modelo, memória, cores, preço Pix]`.

- A foto do modelo vem do mapa `IMG`, pela chave do nome do modelo.
- A foto deve mostrar o aparelho em uma cor disponível no estoque.
- Quando uma versão tem uma única cor, o catálogo usa a foto `"Modelo Cor"` do `IMG`, se ela existir (ex.: `"iPhone 18 Pro Max Bordô"`).
- Fotos novas: WebP 800×800, fundo branco, salvas em `img/` (não use links de outros sites, porque eles quebram).

## Como contribuir

1. Crie uma branch para a sua mudança.
2. Teste abrindo o `index.html` no navegador, de preferência também no celular.
3. Abra um Pull Request para a `main`. Tudo que entra na `main` vai para o site na hora.
