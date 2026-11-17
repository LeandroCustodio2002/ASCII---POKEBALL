<div align="center">
   
# ASCII - POKEBALL

To use this project, I recommend always using an image with the same height and width values, then resizing it to 100x50, since characters do not occupy the same amount of space horizontally and vertically.



[View on pages](https://leandrocustodio2002.github.io/ASCII---POKEBALL/)


# 🔴 Pokébola em ASCII

**Uma imagem de Pokébola redesenhada caractere por caractere, com as cores originais, direto no navegador.**

![p5.js](https://img.shields.io/badge/p5.js-ED225D?logo=p5dotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

<img src="img/result2.jpg" alt="Pokébola renderizada em caracteres ASCII coloridos" width="600">

### 🔗 [Ver a demo ao vivo](https://leandrocustodio2002.github.io/ASCII---POKEBALL/)

</div>

---

## 🎨 O que é

Uma página que carrega uma imagem e a transforma em arte ASCII. Não existe canvas na tela: cada linha da imagem vira uma `div` de texto, e cada pixel vira um caractere pintado com a cor dele.

## ⚙️ Como funciona

1. **Carrega a imagem** com o `loadImage` do p5.js, dentro do `preload()`.
2. **Lê os pixels** com `loadPixels()`, um por um, linha por linha.
3. **Ignora o fundo transparente.** Pixels com alpha abaixo de 10 viram espaço em branco.
4. **Calcula o brilho de cada pixel** pela média de R, G e B.
5. **Troca o brilho por um caractere** da rampa abaixo. Quanto mais claro o pixel, mais "cheio" o caractere:

   ```
   Ñ@#W$9876543210?!abc;:+=-,._
   ```

6. **Pinta cada caractere com a cor original do pixel** e adiciona a linha na página com `createDiv`.

## 📐 Por que 100x50?

Um caractere é mais alto do que largo. Por isso, uma imagem quadrada convertida 1 para 1 sai **esticada na vertical**. A solução é partir de uma imagem quadrada e redimensioná-la para **o dobro de largura em relação à altura** (100x50) antes de converter.

| Imagem 50x50 | Mesma imagem em 100x50 |
|:---:|:---:|
| <img src="img/result1.jpg" alt="Resultado esticado usando imagem 50x50" width="350"> | <img src="img/result2.jpg" alt="Resultado proporcional usando imagem 100x50" width="350"> |

## 🖼️ Como trocar a imagem

Coloque a nova imagem na pasta do projeto e troque o nome do arquivo dentro do `preload()`, em [`sketch.js`](sketch.js):

```js
function preload() {
  img = loadImage('pokeball3.png');
}
```

Para o resultado ficar bom, use uma imagem com **fundo transparente** e redimensionada para **100x50**.

## ▶️ Como rodar localmente

O navegador bloqueia a leitura de pixels de imagens abertas direto pelo `file://`, então sirva a pasta com um servidor local:

```bash
git clone https://github.com/LeandroCustodio2002/ASCII---POKEBALL.git
cd ASCII---POKEBALL
npx serve .
```

Depois abra o endereço que aparecer no terminal.

## 📁 Estrutura

| Arquivo | Função |
|---|---|
| `index.html` | Página e import do p5.js |
| `sketch.js` | Leitura da imagem e conversão para ASCII |
| `style.css` | Fonte monoespaçada e reset de margens |
| `pokeball3.png` | Imagem original da Pokébola (100x50) |
| `img/` | Capturas usadas neste README |

## 🙏 Créditos

Pokémon e a Pokébola são marcas da Nintendo, Game Freak e The Pokémon Company. Este repositório é só um estudo de creative coding.
