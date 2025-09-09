# Vision Tech - Documentação

Bem-vindo à documentação do site da Vision Tech. Este documento serve como um guia completo sobre o projeto, incluindo informações sobre a empresa, os conceitos de ESG, os serviços oferecidos e uma wiki técnica detalhada.

## Sobre a Vision Tech

A Vision Tech acredita que a tecnologia pode ser uma força poderosa para o bem. A empresa oferece soluções de software inovadoras e serviços de consultoria que ajudam outras empresas a integrar práticas de ESG (Environmental, Social, and Governance) em suas operações diárias. O objetivo é capacitar os clientes a alcançar suas metas de sustentabilidade, responsabilidade social e governança ética, promovendo um futuro mais justo e sustentável.

## ESG Explicado

ESG é um acrônimo para Environmental, Social, and Governance (Ambiental, Social e Governança), e se refere aos três pilares centrais usados para medir a sustentabilidade e o impacto ético de um investimento em uma empresa ou negócio.

### Environmental (Ambiental)
Refere-se à forma como uma empresa gerencia e impacta o meio ambiente.

### Social
Avalia a gestão de relações da empresa com seus stakeholders.

### Governance (Governança)
Abrange como a empresa é administrada, suas políticas e transparência.

## Serviços
A Vision Tech oferece consultoria e criação de software de ESG para otimizar a tomada de decisões e reforçar a transparência corporativa.
- **Consultoria de ESG**
- **Software de Monitoramento**

## Recursos e Artigos
O site disponibiliza uma seleção de artigos sobre ESG:
- [Corporate ESG reporting quantity](https://onlinelibrary.wiley.com/doi/full/10.1002/bse.2937)
- [Environmental, social and governance performance and financial risk](https://www.sciencedirect.com/science/article/abs/pii/S0301420721001586)
- [ESG disclosure and financial performance](https://www.sciencedirect.com/science/article/abs/pii/S1057521922002472)
- [Public perceptions of environmental, social, and governance (ESG)](https://www.sciencedirect.com/science/article/abs/pii/S0959652622054142)
- [Integrating Environmental, Social and Governance (ESG) Disclosure for a Sustainable Development](https://onlinelibrary.wiley.com/doi/abs/10.1002/bse.1927)

---

## Wiki Técnica

Esta seção fornece uma análise aprofundada do código-fonte, das dependências e de como customizar o projeto.

<details>
<summary><strong>Análise do Código Fonte</strong></summary>

### `index.html`
O arquivo `index.html` é a espinha dorsal do site. Ele é estruturado em seções semânticas que correspondem às diferentes partes da página.

-   **`<head>`**: Contém metadados, o título da página e links para as folhas de estilo (CSS) e favicons.
-   **`<section class="home">`**: A primeira seção visível, que ocupa a tela inteira (`100vh`). Contém a barra de navegação (`<nav>`) e o conteúdo principal de boas-vindas.
-   **`<section class="esg">`**: Apresenta os três pilares do ESG (Environmental, Social, Governance) em três caixas (`<div class="box">`).
-   **`<section class="consultancy">`**: Descreve os serviços de consultoria e software. Inclui uma galeria de imagens.
-   **`<section class="article">`**: Exibe o artigo mais recente e uma lista de outros artigos relevantes, com links para fontes externas.
-   **`<footer>`**: O rodapé do site, contendo informações de contato, links sociais e de navegação, e o copyright.
-   **Scripts**: No final do `<body>`, são importadas as bibliotecas JavaScript (GSAP) e o script principal (`main.js`). Também inclui o widget de acessibilidade VLibras.

### `css/styles.css`
Este arquivo é responsável por toda a apresentação visual do site.

-   **`@import`**: Importa a fonte "Poppins" do Google Fonts.
-   **Reset Global (`*`)**: Um reset de CSS básico é aplicado para garantir consistência entre navegadores, zerando margens e paddings.
-   **Variáveis de Cor (`:root`)**: Define um esquema de cores centralizado para fácil manutenção.
    -   `--dark-green: #112a34;`
    -   `--green-color: #004047;`
    -   `--white-color: #fff;`
    -   `--text-color: #1d1732;`
-   **Estilos Gerais**: Estilos para `body`, `section`, e classes de utilidade como `.label` e `.heading`.
-   **Componentes**: Cada seção (`.home`, `.esg`, etc.) tem seu próprio bloco de estilo.
-   **Responsividade (`@media`)**: Media queries são usadas para adaptar o layout a diferentes tamanhos de tela (breakpoints em `1020px`, `910px`, `767px`, `607px`, `457px`), garantindo que o site seja funcional em desktops, tablets e celulares.

### `js/main.js`
Este arquivo controla a interatividade e as animações do site usando a biblioteca GSAP.

-   **Menu Mobile**: O código no topo gerencia a abertura e o fechamento do menu de navegação em telas pequenas.
    -   `bars.addEventListener("click", ...)`: Adiciona a classe `.active` ao menu, tornando-o visível.
    -   `close.addEventListener("click", ...)`: Remove a classe `.active` para esconder o menu.
-   **Funções de Animação Genéricas**: O script define funções reutilizáveis para criar animações baseadas em scroll.
    -   `animateContent()`: Anima a entrada do conteúdo inicial da página.
    -   `scrollTirggerAnimation()`: Anima elementos para aparecerem quando o usuário rola a página até eles (efeito de "fade in" para cima).
    -   `swipeAnimation()`: Similar à anterior, mas com um efeito de deslizar ("swipe") lateral.
    -   `galleryAnimation()`: Animação específica para a galeria de imagens.
-   **Chamadas de Animação**: Na parte inferior do arquivo, as funções de animação são chamadas, associando seletores de CSS específicos a cada animação. Por exemplo, `scrollTirggerAnimation(".esg", ...)` aplica a animação de scroll aos elementos da seção ESG.

</details>

<details>
<summary><strong>Dependências</strong></summary>

-   **GSAP (GreenSock Animation Platform)**: A principal biblioteca de animação usada para criar todas as transições suaves e os efeitos de scroll-trigger no site. Inclui o plugin `ScrollTrigger`.
-   **Font Awesome**: Fornece um conjunto de ícones vetoriais utilizados na interface (ex: ícones de redes sociais).
-   **Remixicon**: Outra biblioteca de ícones utilizada para complementar a Font Awesome.
-   **Google Fonts**: Usada para carregar a família de fontes "Poppins", que define a tipografia do site.
-   **VLibras**: Um widget do governo brasileiro que adiciona um tradutor de conteúdo para a Língua Brasileira de Sinais (Libras), tornando o site mais acessível.

</details>

<details>
<summary><strong>Guia de Customização</strong></summary>

### Alterando o Tema de Cores
Para alterar as cores principais do site, edite as variáveis CSS no início do arquivo `css/styles.css`:
```css
:root {
    --dark-green: #112a34; /* Cor de fundo do rodapé */
    --green-color: #004047; /* Cor de destaque principal */
    --white-color: #fff; /* Cor do texto sobre fundos escuros */
    --text-color: #1d1732; /* Cor principal do texto */
}
```

### Adicionando um Novo Artigo
1.  Abra o arquivo `index.html`.
2.  Navegue até a seção `<section class="article">`.
3.  Dentro de `<div class="more-article">`, copie um dos blocos `<div class="box">` existentes.
4.  Cole o bloco copiado e altere o `<h3>` (título), o link `<a>`, e o `<li>` (autor) com as informações do novo artigo.
5.  Altere a imagem em `<img src="...">`.

### Adicionando uma Nova Seção à Página
1.  **HTML**: Adicione uma nova tag `<section>` com uma classe única em `index.html`. Estruture o conteúdo dentro dela.
2.  **CSS**: Crie um novo bloco de estilo para a sua nova classe de seção em `css/styles.css` para definir sua aparência. Não se esqueça de adicionar media queries para garantir a responsividade.
3.  **JavaScript (Opcional)**: Se a nova seção precisar de animações, vá para `js/main.js` e chame uma das funções de animação existentes (ou crie uma nova) com o seletor da sua nova seção.
4.  **Navegação**: Adicione um link para a nova seção na barra de navegação (`<nav>`) em `index.html`.

</details>
