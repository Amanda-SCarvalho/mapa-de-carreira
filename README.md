#  Mapa de Carreira

Página de portfólio e trajetória profissional orientada por dados, com conteúdo carregado dinamicamente a partir de um arquivo JSON.

## Sobre o projeto

O **Mapa de Carreira** é uma página web estática que exibe de forma visual e organizada a jornada profissional de um desenvolvedor — incluindo etapas de carreira, habilidades técnicas, soft skills e idiomas.

A arquitetura segue uma separação clara de responsabilidades:

- **HTML** — estrutura e marcação semântica da página
- **JSON** (`assets/data/carreira.json`) — fonte de dados editável com textos, listas e configurações
- **JavaScript** (`assets/js/carreira-json.js`) — lê o JSON via `fetch` e injeta os dados nos elementos da página

Essa abordagem permite atualizar todo o conteúdo sem alterar o HTML, tornando a manutenção simples e acessível.

## 📁 Estrutura de arquivos

```
mapa-de-carreira/
├── index.html                  # Estrutura principal da página
├── favicon.ico
└── assets/
    ├── data/
    │   └── carreira.json       # Dados editáveis (perfil, carreira, skills, idiomas)
    ├── js/
    │   └── carreira-json.js    # Script que carrega e renderiza os dados
    ├── css/
    │   └── bootstrap-*.css     # Temas visuais disponíveis
    └── images/
        └── profile.png         # Foto de perfil
```

## ✏️ Como personalizar

Todo o conteúdo da página é controlado pelo arquivo `assets/data/carreira.json`. Edite os campos abaixo para adaptar ao seu perfil:

| Campo | Descrição |
|---|---|
| `seo` | Título, descrição e URL canônica para SEO e Open Graph |
| `profile` | Nome, headline, resumo, foto e link do currículo em PDF |
| `contacts` | Links de contato (GitHub, LinkedIn, e-mail etc.) |
| `careerSteps` | Etapas da carreira com título, descrição, soft skills e roadmap |
| `skillGroups` | Grupos de habilidades técnicas com nível percentual |
| `otherSkills` | Lista de competências complementares |
| `languages` | Idiomas e respectivos níveis |

## 🚀 Como executar

> ⚠️ O `fetch` do JSON **não funciona ao abrir o arquivo diretamente no navegador** (`file://`). Use um servidor local ou publique online.

### Opção 1 — Extensão Live Server (VS Code)

1. Instale a extensão **Live Server** no VS Code
2. Clique com o botão direito em `index.html`
3. Selecione **"Open with Live Server"**

### Opção 2 — Servidor local com Python

```bash
# Python 3
python -m http.server 8080
```

Acesse `http://localhost:8080` no navegador.

### Opção 3 — GitHub Pages (recomendado para publicar)

1. Suba o projeto para um repositório no GitHub
2. Vá em **Settings → Pages**
3. Selecione a branch `main` como fonte
4. A página ficará disponível em `https://seu-usuario.github.io/nome-do-repositorio`

## 🎨 Trocando o tema visual

O projeto inclui 6 arquivos de tema CSS (`bootstrap-1.css` a `bootstrap-6.css`). Para trocar o tema, altere o atributo `href` da tag abaixo no `index.html`:

```html
<link id="theme-style" rel="stylesheet" href="assets/css/bootstrap-5.css">
```

## Acessibilidade

A página foi construída com boas práticas de acessibilidade:

- Link de "Pular para o conteúdo principal" para navegação por teclado
- Uso semântico de `<header>`, `<main>`, `<section>`, `<aside>`, `<article>` e `<nav>`
- Atributos `aria-label` e `aria-labelledby` nas seções e listas
- Textos alternativos nas imagens
- Barras de progresso com `aria-valuenow`, `aria-valuemin` e `aria-valuemax`

## Tecnologias utilizadas

- HTML5 semântico
- CSS3 / Bootstrap (tema customizado)
- JavaScript puro (ES6+)
- Google Fonts (Roboto)
- JSON como fonte de dados

## 📄 Licença

Este projeto é de uso pessoal e educacional. Sinta-se livre para adaptá-lo ao seu próprio mapa de carreira.
