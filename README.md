# Retro Pop 🍿

Site da **Retro Pop**, uma banca de pipoca gourmet montada por alunos para a feira da **Escola SESI SENAI Jardim Colorado**.

Página única, sem build e sem dependências: é só abrir o `index.html` no navegador.

## O que tem aqui

- `index.html` — o site inteiro (HTML + CSS + JS num arquivo só)

## Como funciona a arte

Nada de imagem: toda a pixel art é desenhada em `<canvas>` por um motor próprio no final do arquivo.

| Função | O que faz |
| --- | --- |
| `makePuff(seed, pal, S)` | Gera uma pipoca a partir de lóbulos aleatórios, com contorno preto, sombra e brilho |
| `makeBucket(pal, w, h)` | Desenha o balde listrado linha por linha, com a inclinação das laterais |
| `moundLayout(...)` | Distribui as pipocas em três camadas, formando o monte em cima do balde |
| `makeBadgeDisc` / `makeBadgeText` | O selo redondo e as letras (fonte bitmap 5×7 feita à mão, só com R, E, T, O e P) |
| `paintArt(canvas, opt)` | Junta tudo — usado nos cards de sabor, no logo do menu, no rodapé e na seção de encomenda |

O herói usa as mesmas funções, mas animado pelo scroll: um grão estoura, vira pipoca, se multiplica, o balde sobe e o selo aparece.

## Mexer no cardápio

Os sabores ficam no array `FLAVORS`, dentro do `<script>`. Cada item define nome, descrição, preço, nível de ardência e as cores do balde e da pipoca:

```js
{ n:"Caramelo Crocante", d:"Açúcar queimado na panela...",
  p:"R$ 8", heat:1, flag:"",
  pop:{fill:"#D89A46",hi:"#F0BE72",sh:"#9E6721"},
  bucket:{body:"#E08A2E",bodyDk:"#A85F17",stripe:"#FFF6E8",edge:"#F3C489"} }
```

Mudou as cores, a arte do card muda junto — não precisa editar imagem nenhuma.

## Ainda falta preencher

- A data e o horário da feira (hoje está "Data a confirmar", na seção **Onde e quando**)
- Confirmar os preços e os tamanhos
- O formulário de encomenda só mostra um aviso na tela; ele ainda não envia nada pra lugar nenhum
