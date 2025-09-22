# GRUPO-04

**Projeto:** Página hospedada em GitHub Pages.

**Link do projeto:** [https://hakizao6074.github.io/GRUPO-04/](https://hakizao6074.github.io/GRUPO-04/)

---

## Descrição

Este repositório contém a página do *Grupo 04*. Abaixo você encontra instruções rápidas de como visualizar a página, como rodar localmente (se aplicável) e um pequeno exemplo de animação de máquina de escrever (typing) que escreve o trecho pedido da música.

> Trecho exibido na animação: "daquela musica a marvada da pinga que eu me atrapaho eu bebe e ali mesmo eu caio"

---

## Como visualizar

1. Abra o link acima para ver a versão publicada no GitHub Pages.
2. Para rodar localmente, clone o repositório e abra o arquivo `index.html` no navegador.

---

## Exemplo: animação de "typing" (arquivo HTML de demonstração)

Você pode criar um arquivo `typing-demo.html` com o conteúdo abaixo e abri-lo no navegador para ver a animação de escrita do trecho da música.

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Typing Demo - GRUPO-04</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; display:flex; align-items:center; justify-content:center; height:100vh; margin:0; background:#0f172a; color:#e6edf3 }
    .card { background:rgba(255,255,255,0.04); padding:2rem; border-radius:12px; box-shadow:0 6px 18px rgba(2,6,23,0.6); max-width:900px }
    .typewriter { font-size:1.25rem; line-height:1.6; white-space:pre-wrap; min-height:3em }
    /* cursor */
    .cursor { display:inline-block; width:.7ch; animation:blink 1s steps(2) infinite; }
    @keyframes blink { 50% { opacity:0 } }
  </style>
</head>
<body>
  <div class="card">
    <h2>Demonstração — Animação de escrevendo</h2>
    <p>Link do projeto: <a href="https://hakizao6074.github.io/GRUPO-04/" target="_blank">https://hakizao6074.github.io/GRUPO-04/</a></p>

    <div id="type" class="typewriter"></div>
  </div>

  <script>
    const text = `daquela musica a marvada da pinga que eu me atrapaho eu bebe e ali mesmo eu caio`;
    const target = document.getElementById('type');
    const cursor = document.createElement('span');
    cursor.className = 'cursor';
    cursor.textContent = '|';
    target.appendChild(cursor);

    let i = 0;
    function typeNext() {
      if (i < text.length) {
        // insere caractere antes do cursor
        cursor.insertAdjacentText('beforebegin', text[i]);
        i++;
        // velocidade levemente variável para parecer mais natural
        const delay = 40 + Math.random() * 80;
        setTimeout(typeNext, delay);
      } else {
        // opcional: piscar cursor por mais tempo ao final
        cursor.style.animation = 'blink 0.6s steps(2) infinite';
      }
    }
    // começa a digitar após pequeno delay
    setTimeout(typeNext, 600);
  </script>
</body>
</html>
