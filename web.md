## **Introdução à web**

Esteja você apenas visitando um site simples ou usando um navegador para interagir com um aplicativo que controla processos complexos, as tecnologias da Web se tornaram nossa interface para muito do que fazemos hoje. Eles evoluíram muito ao longo dos anos para agora fornecer serviços bancários, serviços públicos, compras, serviços de alimentação e bebidas, mídia social e muito mais; todos os quais têm aplicativos da web complexos nos bastidores, mas parecem fazer com que pareça fácil com suas interfaces amigáveis. O gerenciamento desses serviços também é geralmente online, fornecendo às pessoas dessas empresas a capacidade de gerenciar esses sites.

Quando você "navega" em um site usando `http://` ou `https://` (o equivalente criptografado **s**seguro), uma solicitação é enviada ao servidor da Web que contém o aplicativo da Web. Normalmente, ele responderá com conteúdo HTML, que seu navegador da Web usa como ponto de partida do conteúdo a ser exibido na tela e os arquivos associados a serem carregados. Eles geralmente incluem CSS (arquivos para estilizar o conteúdo), imagens para colocar na página e JavaScript (arquivos para tornar a página mais interativa). Vamos olhar para estes.

**HTML**, abreviação de Hyper Text Markup Language, geralmente é o primeiro conjunto de conteúdo a ser retornado ao seu navegador e é usado para descrever o layout de uma página e seu conteúdo. Ele descreve quais arquivos de imagem são necessários, além de arquivos CSS e JavaScript também, para estilizar a página e adicionar interatividade extra, além de elementos de formulário com os quais você pode interagir (como os campos de e-mail e senha que você usaria para fazer login).

**CSS**, ou Cascading Style Sheets, são os arquivos que descrevem a forma como o conteúdo é exibido. Eles fornecem uma maneira de 'estilizar' elementos, como especificar posições, tamanhos, cores ou outras propriedades que afetam a forma como os elementos aparecem na página.

**JavaScript**, esta é uma linguagem de programação poderosa que pode tornar a página realmente interativa, manipular eventos, reproduzir arquivos de mídia, renderizar animações e muito mais.

## **Visualizando no seu navegador**

Os idiomas mencionados acima fornecem a base da interface do usuário que você vê à sua frente, interpretada **localmente** (no seu computador) no navegador. Pense neles como um conjunto de instruções sobre como *descrever* uma página da Web, além de sua aparência e comportamento. Podemos visualizar o conteúdo desses arquivos e de outros clicando com o botão direito do mouse na página e escolhendo `Inspecionar` ou `Ver código fonte`. Isso mostrará o conteúdo HTML (vale a pena estudar para entender a estrutura da página) e permitirá a navegação para os arquivos extras, como CSS, JavaScript e muito mais. Não se deixe levar pelas incógnitas, muitos dos termos nessas línguas são bastante lógicos.

O CSS e o JavaScript geralmente são carregados na seção `<head>` e o conteúdo que você vê na página da Web na seção `<body>` . O método `Inspect` é particularmente útil, pois conforme você destaca elementos, ele destaca o elemento renderizado correspondente na página.

Dentro da própria página, sempre que você realizar uma nova ação para solicitar um novo conteúdo, como ir para uma nova página, o ciclo de 'solicitação enviada ao servidor' e 'resposta recebida pelo navegador' (que inclui o carregamento de todo novo HTML, CSS, JavaScript e outros arquivos) começa novamente.

Embora valha a pena aprender sobre CSS, do ponto de vista da vulnerabilidade, HTML e JavaScript serão mais interessantes para nós, pois nos permitem encontrar novas páginas para visitar e codificar que descreve como a página funciona. Entre estes podemos encontrar dados sensíveis ou descuidos que nos permitem manipular, quebrar e 'hackear' o site.

> Os aplicativos da web modernos são uma combinação de tecnologias do lado do cliente e do lado do servidor, e ambos podem ser atacados e aproveitados por criminosos cibernéticos. Uma verificação de segurança implementada em ambos os lados pode ser ignorada, portanto, verificações e balanços são frequentemente aplicados em ambos!


Continua...
