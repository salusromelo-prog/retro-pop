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
{ n:"Ninho", d:"Leite em pó por cima, bem cremoso e docinho...",
  p:"Cremoso", heat:2, flag:"",
  pop:{fill:"#FBF0DA",hi:"#FFFBEF",sh:"#D9C6A2"},
  bucket:{body:"#4E9AA6",bodyDk:"#2E6C77",stripe:"#FFF6E8",edge:"#A5CFD6"} }
```

`heat` aqui é a doçura (0 a 3) e `p` é o descritor curto que aparece no rodapé do card.

Mudou as cores, a arte do card muda junto — não precisa editar imagem nenhuma.

## O que a banca vende

Três sabores em saquinho fechado, um tamanho só:

| Sabor | Preço |
| --- | --- |
| Sal | R$ 10 |
| Chocolate | R$ 15 |
| Ninho | R$ 15 |

A pipoca é preparada antes e vendida embalada, não estourada na hora.
Pagamento em dinheiro e pix (maquininha de cartão ainda em aberto).

## Ainda falta preencher

- **A data e o horário da feira** — hoje está "Data a confirmar", na seção *Onde e quando*
- **A maquininha** — confirmar se vai ter cartão ou não
- **Preço dos combos** — a seção de combos mostra a quantidade, não o valor; hoje o preço é só a soma dos saquinhos
