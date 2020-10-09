# store-framework-template

Pontos antes de iniciar:

- Entender do negócio
- O que agrega valor?
- Qual o foco final?
- Quais as necessidades do negócio e porques?

**Curiosidade**: O nome VTEX vem da primeira loja de roupa montada pelos fundadores que era uma Vitrine TEXtil para quem queria comprar tecidos online.

## O que é e para que serve a VTEX?

É uma empresa que oferece um SolaaS (Solution as a Service) no ramo de e-commerce (lojas virtuais). Dentro desta plataforma existem várias estruturas e funcionalidades que podem ser utilizadas pelos lojistas para impulsionar, controlar, escalar, melhorar vendas e presença online no mercado em que atuam.

A VTEX oferece toda a estrutura necessária para o desenvolvimento de uma loja virtual permitindo cadastro de produtos, integrações, acompanhamento de relatórios e diversas outras soluções para que você possa crescer sua loja online com qualidade. Além de toda a funcionalidade para o cliente e empresa final, a VTEX também se preocupa em ter uma estrutura acessível e organizada para desenvolvedores e parceiros terem a oportunidade de criar, personalizar e melhorar as lojas de diversas formas.

[https://www.youtube.com/watch?v=JgkrlaF52WQ](https://www.youtube.com/watch?v=JgkrlaF52WQ)

[Overview completo da plataforma VTEX](https://developers.vtex.com/docs/getting-started-platform-overview)

![https://files.readme.io/946c5ec-Screen_Shot_2020-01-16_at_11.20.32.png](https://files.readme.io/946c5ec-Screen_Shot_2020-01-16_at_11.20.32.png)

## VTEX IO

É a plataforma de desenvolvimento para criar personalizações e implementações na VTEX, permite a criação de apps front/back seguindo os padrões da plataforma para evoluir de forma consistente. Antigamente era utilizado o VTEX CMS que vem sendo descontinuado.

![https://files.readme.io/f883472-Screen_Shot_2020-01-16_at_11.19.47.png](https://files.readme.io/f883472-Screen_Shot_2020-01-16_at_11.19.47.png)

### VTEX IO Store Framework

É um conjunto de ferramentas e "blocos" para que você possa montar a estrutura de uma loja da maneira mais rápida possível utilizando React. Você pode conferir a [lista de todos os componentes](https://vtex.io/docs/components/all/).

Seguindo a ideia de que várias lojas possuem muitas estruturas similares o Store Framework reúne esses componentes e abstrai cada um deles para que você possa replicar em qualquer loja. Os componentes criados na Store são responsáveis por construir a parte "frontal" da loja e usam como padrão o [JSON](http://www.json.org/json-pt.html).

## O que pode ser construido com o VTEX IO

- Front-end personalizado da loja utilizando React e componentes.
- Admin Apps, personalizações específicas para cada loja utilizando os dados disponibilizados pela VTEX, algo como "componentes personalizados próprios"
- Back-end apps, construção de serviços desenvolvidos em Node ou .NET Core.
- Pixels apps personalizados para coletar dados de dentro da loja.
- Mobile Apps, para a loja estar disponivel em devices mobiles para os clientes

Customizações avançadas são um poucos limitadas e precisam de permissão para serem inseridas no VTEX IO.

### Básico para iniciar o desenvolvimento em VTEX IO

- Instalar o [GIT](https://git-scm.com/)
- Instalar o [Node.js](https://nodejs.org/en/) e o gerenciador de pacotes [Yarn](https://classic.yarnpkg.com/pt-BR/docs/install)
- Instalar o [Toolbet](https://github.com/vtex/toolbelt) da VTEX (yarn global add vtex)
- Criar (caso não tenha) e logar em uma conta VTEX
- Linkar seus arquivos locais com a plataforma

A VTEX IO possui três workspaces padrões:

- master, production e development

## O que são workspaces?

São ambientes controlados que criam uma réplica da loja online do cliente para que você possa trabalhar em um ambiente seguro sem afetar o usuário final com suas modificações, quando tudo estiver correto basta enviar para a loja oficial. Todos os workspaces são sincronizados com a plataforma que está online.

Se você está acostumado com o Github pense em workspaces como branches.

O workspace público oficial sempre terá o nome de Master. O Master é o workspace padrão quando você loga em sua conta no vtex cli, lembre-se de mudar para um de desenvolvimento sempre que necessário.

### Como criar um workspace de desenvolvimento

```bash
vtex use nomedoworkspace
```

## Blocos

São abstrações na Store Framework, são basicamente "pedaços" mínimos da loja para que você possa uni-lós e chegar a um resultado final. Os blocos seguem um conceito similar ao de componentes, que são abstrações que declaram um pedaço mínimo de funcionalidade para ser trabalhado.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0827e7db-5c07-4fc7-aafe-c6e72d3a843d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0827e7db-5c07-4fc7-aafe-c6e72d3a843d/Untitled.png)

Os blocos padrões da Store Framewok possuem 4 niveis de personalização:

- Estilo semântico (style)
- Propriedades (props)
- Classes CSS (handles)
- Children (children)

## Flex layout

Elemento para estruturação dos blocos dentro de sua loja, seguindo o conceito de linhas e colunas para alinhar elementos dentro da estrutura. Existem duas tags básicas no flexlayout: row (linha), col (coluna). Se você conhece a propriedade flexbox do CSS essa estrutura segue o mesmo conceito.

## Links

Site VTEX IO: [https://vtex.io/](https://vtex.io/)

Introdução VTEX IO: [https://vtex.io/docs/introduction](https://vtex.io/docs/introduction)

Releases VTEX IO: [https://vtex.io/docs/releases/](https://vtex.io/docs/releases/)

Repositório da documentação: [https://github.com/vtex-apps/io-documentation](https://github.com/vtex-apps/io-documentation)

Treinamento VTEX IO: [https://lab.github.com/vtex-trainings/store-framework](https://lab.github.com/vtex-trainings/store-framework)

## Notas:

- Style guides ficam em config/styles.json
- A extensão de arquivo JSONC é um json que permite comentários
- Para criar estilos customizados é necessários sobrescrever os estilos padrões com [CSS customizations](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization/)
- Nunca utilize o `flex-layout` sozinho, sempre adicione alguma propriedade (row, col...)
- [Shelf](https://vtex.io/docs/app/vtex.shelf@1.44.0/) sempre declara um [product-summary](https://vtex.io/docs/components/product/vtex.product-summary@2.61.0/) em seu contexto
- Normalmente a maioria dos itens criados serão uma junção de vários blocos, css customizations e em alguns casos admin apps.
- Os blocos do Store Framework usam o padrão de [Tachyons](https://tachyons.io/) para fazer as estilizações
- Sempre que possível utilize o padrão css do styles.json dentro do configs
- Iframes só são permitidos em páginas customizadas

## Comandos mais usados:

[CLI Commands](https://vtex.io/docs/recipes/development/vtex-io-cli-installation-and-command-reference/)

```jsx
vtex login ContaVTEX // Autenticar conta na loja
vtex whoami // Identifica o workspace que está usando
vtex browse // Abre o workspace no navegador
vtex link // Ativar o link que está trabalhando
```
