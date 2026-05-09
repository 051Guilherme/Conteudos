# 🌐 HTML — Estrutura, Semântica e Boas Práticas

> Anotações de referência rápida sobre HTML: desde a estrutura básica até semântica e acessibilidade.

---

## 📋 Índice

- [Estrutura Básica](#estrutura-básica)
- [Tags de Metadados (Head)](#tags-de-metadados-head)
- [Tags de Texto](#tags-de-texto)
- [Listas](#listas)
- [Links e Âncoras](#links-e-âncoras)
- [Imagens e Mídia](#imagens-e-mídia)
- [Tabelas](#tabelas)
- [Formulários](#formulários)
- [HTML Semântico](#html-semântico)
- [Atributos Globais](#atributos-globais)
- [Acessibilidade (a11y)](#acessibilidade-a11y)
- [Boas Práticas](#boas-práticas)

---

## Estrutura Básica

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Título da Página</title>
  </head>
  <body>
    <!-- Conteúdo aqui -->
  </body>
</html>
```

| Elemento | Descrição |
|---|---|
| `<!DOCTYPE html>` | Declara o documento como HTML5 |
| `<html lang="">` | Elemento raiz; `lang` define o idioma da página |
| `<head>` | Metadados da página (não visível ao usuário) |
| `<body>` | Conteúdo visível da página |

---

## Tags de Metadados (Head)

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="Descrição da página para SEO" />
<meta name="author" content="Nome do Autor" />

<!-- Open Graph (redes sociais) -->
<meta property="og:title" content="Título" />
<meta property="og:description" content="Descrição" />
<meta property="og:image" content="url-da-imagem.jpg" />

<!-- CSS e Favicon -->
<link rel="stylesheet" href="style.css" />
<link rel="icon" href="favicon.ico" type="image/x-icon" />

<!-- JavaScript -->
<script src="script.js" defer></script>
```

> 💡 **Dica:** Use `defer` no `<script>` para que o JS carregue sem bloquear o HTML.

---

## Tags de Texto

```html
<!-- Títulos (h1 a h6) -->
<h1>Título Principal</h1>
<h2>Subtítulo</h2>
<h3>Seção</h3>

<!-- Parágrafo -->
<p>Texto do parágrafo.</p>

<!-- Formatação inline -->
<strong>Negrito semântico (importante)</strong>
<em>Itálico semântico (ênfase)</em>
<b>Negrito visual</b>
<i>Itálico visual</i>
<u>Sublinhado</u>
<s>Texto tachado</s>
<mark>Texto destacado</mark>
<small>Texto menor</small>
<sup>Sobrescrito</sup> e <sub>Subscrito</sub>

<!-- Código -->
<code>código inline</code>
<pre><code>bloco de código</code></pre>

<!-- Citações -->
<blockquote cite="url-da-fonte">Citação longa.</blockquote>
<q>Citação curta inline.</q>

<!-- Quebra e linha horizontal -->
<br />
<hr />
```

---

## Listas

```html
<!-- Lista não ordenada -->
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<!-- Lista ordenada -->
<ol>
  <li>Primeiro</li>
  <li>Segundo</li>
</ol>

<!-- Lista de definição -->
<dl>
  <dt>Termo</dt>
  <dd>Definição do termo</dd>
</dl>
```

---

## Links e Âncoras

```html
<!-- Link externo -->
<a href="https://exemplo.com" target="_blank" rel="noopener noreferrer">Visitar site</a>

<!-- Link interno (mesma página) -->
<a href="#secao-id">Ir para a seção</a>

<!-- Link para email e telefone -->
<a href="mailto:email@exemplo.com">Enviar e-mail</a>
<a href="tel:+5511999999999">Ligar</a>

<!-- Link para download -->
<a href="arquivo.pdf" download>Baixar PDF</a>
```

> ⚠️ **Importante:** Sempre use `rel="noopener noreferrer"` em links com `target="_blank"` por segurança.

---

## Imagens e Mídia

```html
<!-- Imagem -->
<img src="foto.jpg" alt="Descrição da imagem" width="800" height="600" loading="lazy" />

<!-- Imagem responsiva -->
<picture>
  <source srcset="imagem-large.webp" media="(min-width: 800px)" type="image/webp" />
  <source srcset="imagem-small.webp" type="image/webp" />
  <img src="imagem-fallback.jpg" alt="Descrição" />
</picture>

<!-- Figura com legenda -->
<figure>
  <img src="grafico.png" alt="Gráfico de vendas" />
  <figcaption>Gráfico de vendas do trimestre.</figcaption>
</figure>

<!-- Vídeo -->
<video src="video.mp4" controls width="640" poster="thumbnail.jpg">
  <track kind="subtitles" src="legendas.vtt" srclang="pt" label="Português" />
  Seu navegador não suporta vídeo HTML5.
</video>

<!-- Áudio -->
<audio src="audio.mp3" controls>
  Seu navegador não suporta áudio HTML5.
</audio>
```

---

## Tabelas

```html
<table>
  <caption>Legenda da Tabela</caption>
  <thead>
    <tr>
      <th scope="col">Nome</th>
      <th scope="col">Idade</th>
      <th scope="col">Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ana</td>
      <td>28</td>
      <td>São Paulo</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Total: 1 registro</td>
    </tr>
  </tfoot>
</table>
```

> 💡 Use `scope="col"` ou `scope="row"` nos `<th>` para melhor acessibilidade.

---

## Formulários

```html
<form action="/enviar" method="POST">
  <!-- Texto -->
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome" placeholder="Seu nome" required />

  <!-- E-mail -->
  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required />

  <!-- Senha -->
  <label for="senha">Senha:</label>
  <input type="password" id="senha" name="senha" minlength="8" required />

  <!-- Número -->
  <input type="number" name="quantidade" min="1" max="100" />

  <!-- Checkbox -->
  <input type="checkbox" id="aceito" name="aceito" />
  <label for="aceito">Aceito os termos</label>

  <!-- Radio -->
  <input type="radio" id="masculino" name="genero" value="m" />
  <label for="masculino">Masculino</label>

  <!-- Select -->
  <select name="estado">
    <option value="">Selecione...</option>
    <option value="sp">São Paulo</option>
    <option value="rj">Rio de Janeiro</option>
  </select>

  <!-- Textarea -->
  <textarea name="mensagem" rows="4" cols="50"></textarea>

  <!-- Botões -->
  <button type="submit">Enviar</button>
  <button type="reset">Limpar</button>
  <button type="button">Ação JS</button>
</form>
```

### Tipos de `<input>` mais usados

| Tipo | Uso |
|---|---|
| `text` | Texto simples |
| `email` | Endereço de e-mail |
| `password` | Senha (oculta) |
| `number` | Número |
| `tel` | Telefone |
| `url` | URL |
| `date` | Data |
| `time` | Hora |
| `file` | Upload de arquivo |
| `checkbox` | Caixa de seleção |
| `radio` | Opção única |
| `range` | Controle deslizante |
| `color` | Seletor de cor |
| `hidden` | Campo oculto |
| `search` | Campo de busca |

---

## HTML Semântico

Elementos semânticos deixam o código mais legível e acessível, além de melhorar o SEO.

```html
<body>
  <header>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/sobre">Sobre</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <article>
      <header>
        <h1>Título do Artigo</h1>
        <time datetime="2025-01-15">15 de Janeiro de 2025</time>
      </header>

      <section>
        <h2>Seção do Artigo</h2>
        <p>Conteúdo...</p>
      </section>

      <aside>
        <p>Conteúdo relacionado ou lateral.</p>
      </aside>
    </article>
  </main>

  <footer>
    <p>&copy; 2025 Meu Site</p>
  </footer>
</body>
```

### Referência de elementos semânticos

| Elemento | Uso |
|---|---|
| `<header>` | Cabeçalho da página ou de uma seção |
| `<nav>` | Bloco de navegação/links principais |
| `<main>` | Conteúdo principal (único por página) |
| `<article>` | Conteúdo independente e reutilizável |
| `<section>` | Seção temática de conteúdo |
| `<aside>` | Conteúdo lateral ou complementar |
| `<footer>` | Rodapé da página ou de uma seção |
| `<figure>` | Conteúdo visual com legenda opcional |
| `<figcaption>` | Legenda de um `<figure>` |
| `<time>` | Data ou hora legível por máquinas |
| `<address>` | Informações de contato do autor |
| `<details>` | Bloco de conteúdo expansível |
| `<summary>` | Título visível de um `<details>` |

---

## Atributos Globais

Atributos que podem ser usados em qualquer elemento HTML:

| Atributo | Descrição |
|---|---|
| `id` | Identificador único do elemento |
| `class` | Classe(s) CSS do elemento |
| `style` | Estilo inline |
| `title` | Dica de ferramenta (tooltip) |
| `lang` | Idioma do conteúdo do elemento |
| `tabindex` | Ordem de foco via teclado |
| `hidden` | Oculta o elemento |
| `data-*` | Atributos de dados personalizados |
| `contenteditable` | Torna o conteúdo editável |
| `draggable` | Permite arrastar o elemento |
| `spellcheck` | Ativa/desativa verificação ortográfica |

```html
<!-- Exemplo de data-* -->
<button data-id="42" data-acao="deletar">Deletar</button>

<!-- Acessado via JS -->
<!-- element.dataset.id → "42" -->
<!-- element.dataset.acao → "deletar" -->
```

---

## Acessibilidade (a11y)

```html
<!-- ARIA Roles -->
<div role="alert">Mensagem de erro!</div>
<nav role="navigation" aria-label="Menu principal"></nav>

<!-- ARIA States e Properties -->
<button aria-expanded="false" aria-controls="menu">Abrir Menu</button>
<div id="menu" aria-hidden="true">...</div>

<!-- Texto alternativo para ícones -->
<button>
  <img src="lixeira.svg" alt="" aria-hidden="true" />
  <span>Deletar item</span>
</button>

<!-- Texto visível apenas para leitores de tela -->
<span class="sr-only">Informação para leitores de tela</span>

<!-- Associação de label e input -->
<label for="busca">Buscar:</label>
<input type="search" id="busca" aria-describedby="busca-dica" />
<p id="busca-dica">Digite ao menos 3 caracteres.</p>
```

---

## Boas Práticas

### ✅ Faça

- Use sempre `<!DOCTYPE html>` no início do documento
- Defina o idioma com `lang="pt-BR"` na tag `<html>`
- Sempre inclua o atributo `alt` em imagens
- Use elementos semânticos em vez de `<div>` para tudo
- Associe `<label>` a cada `<input>` com `for` + `id`
- Use `loading="lazy"` em imagens abaixo do fold
- Valide o HTML em [validator.w3.org](https://validator.w3.org)
- Use hierarquia correta de títulos (`h1` → `h2` → `h3`...)
- Prefira `<button>` para ações e `<a>` para navegação

### ❌ Evite

- Usar `<br>` para criar espaçamento (use CSS)
- Usar `<table>` para layout de página
- Omitir o `alt` em imagens (deixe `alt=""` se for decorativa)
- Usar `<b>` e `<i>` onde `<strong>` e `<em>` fazem mais sentido
- Ter mais de um `<h1>` por página
- Usar `<div>` e `<span>` onde existe um elemento semântico adequado
- Colocar `<script>` no `<head>` sem `defer` ou `async`

---
