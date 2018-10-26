# calculadora
Calculadora simples utilizando o **jQuery Mobile (JQM)**

Demonstração: [CALCULADORA](https://doni7brandao.github.io/calculadora/)

Aqui está uma maneira fácil de entender o projeto do jQuery Mobile (JQM), uma calculadora simples. O aplicativo inteiro consiste em uma única página e cerca de 200 linhas de código. Vamos começar nossa explicação com o Kernel que está perto do começo do arquivo app.js.

**O Kernel**

A função do Kernel é unir arquivos HTML e JavaScript. Mapeamos todos os eventos da página do JQM para o Kernel. Primeiro, atribuímos o nome do evento à variável *eventType*. Em seguida, extraímos o nome do arquivo JavaScript da página do atributo psuedo, "data-rockncoder-jspage" e atribuímos à variável pageName . As linhas finais do Kernel chamam o manipulador do evento em seu código de página, apenas se o manipulador existir. A instrução *if* simplesmente garante que haja um manipulador antes de ser chamado. Rockncoder.App segue o kernel. Sua única função é ligar todos os eventos da página e direcioná-los para o Kernel.

**O código da página**

Em seguida vem o código da página em RocknCoder.Pages.calculator. Usamos um literal de objeto para armazenar todo o código das páginas. Em algum momento no futuro eu estarei alterando este código para usar uma função e não um objeto literal, mas eu tenho feito por tanto tempo assim, o hábito é difícil de quebrar. Uma implementação melhor seria fazer algo como um "Revealing Module Pattern", que também nos daria a capacidade de ocultar nossas variáveis locais.

No código da página, lidamos com três eventos: *pageinit, pageshow e pagehide*. Qualquer evento que não esteja definido não é chamado pelo Kernel. O primeiro manipulador de eventos, pageinit, é o equivalente do JQM ao evento de documento pronto do jQuery. Este é o lugar para fazer qualquer código de inicialização no nível da página. Aqui nós inicializamos nosso hider da barra de endereços do Android. O segundo evento, pagehow, é chamado depois que o JQM renderiza a página. Neste manipulador, inicializamos a calculadora, a mal chamada *RocknCoder.Display*, e ligamos todas as teclas da calculadora. O evento final é o *pagehide*, que usamos para desengatar os eventos. Verdade seja dita, este evento provavelmente nunca será chamado, pois há apenas uma página e o JQM não terá nenhuma página para alternar e, portanto, não há necessidade de ocultar a página atual.

Fonte Original: http://therockncoder.blogspot.com/2012/05/jquery-mobile-calculator.html
