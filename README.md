# AWS Step Functions: um (não tão breve) resumo

Um aplicativo de smartphone pode ser um monolito (um único sistema) ou dividido em microsserviços.

Por exemplo, um aplicativo de entrega de comida é composto de:
1. Uma API de gerenciamento de usuários;
2. Um gerenciador de notificações *push*;
3. Uma API de gerenciamento de estado do pedido.

Existe um **fluxo** entre os microsserviços, ou seja, um depende do outro.
E como fazer um se comunicar com o outro, se cada sistema é como uma ilha?

Para cumprir este papel, existem o **serviço de mensageria**.
Assim que algo acontece, ele publica uma mensagem e os outros sistemas ouvem essa mensagem.

As partes do serviço de mensageria são:
- **Publisher** (publicador): É o "carteiro" que leva mensagens de um sistema para o outro e determina ações;
- **Subscriber** (inscrito): É um sistema que está inscrito para receber mensagens do *publisher*.

E é deste raciocínio que foi criado o AWS Step Functions: **para cada passo (*step*), um conjunto de funções (*functions*)**.

Com uma vantagem: em vez de se usar código, utiliza-se o método clica-e-arrasta, comum em interfaces gráficas.

E os sistemas são os próprios serviços da AWS.

"O Step Functions é um serviço de fluxo de trabalho visual (...) para desenvolver aplicações distribuídas, automatizar processos, orquestrar microsserviços e criar pipelines de dados e machine learning (ML)."

Site oficial: aws.amazon.com/pt/step-functions

Benefícios do Step Functions:
- Integração rápida;
- Automação simples;
- Processar dados sob demanda;
- Visualização da arquitetura orientada por eventos.

Para acessá-lo a partir da página inicial, vá em Serviços → Integração de Aplicativos → Step Functions.
Neste momento, você também pode favoritá-lo para ele sempre aparecer no topo da página.

Um projeto de AWS Step Functions se chama **Máquina de Estado**, e vai controlar o fluxo de trabalho (***Workflow***) do sistema.
Há várias opções de fluxos pré-prontos, todos separados por categorias, e que você pode ou não editar. Mas você também pode, se preferir, fazer um do zero.
Porém, para quem é iniciante em Step Functions, há um fluxo de trabalho pré-pronto extremamente simples, que ensina a fazer um *Hello World* com apenas alguns cliques e em apenas três minutos.

Ao selecionar a sua opção, você é levado ao Workflow Studio, que é a ferramenta de edição de projetos do Step Functions, e se você optou por fazer um *Hello World*, você terá um *tour* guiado. 
O lado esquerdo do estúdio contém as ações, fluxos e padrões; e o lado direito é uma tela em branco o fluxo de trabalho que você vai montar.

Você deve arrastar as ações, fluxos e padrões do lado esquerdo para o direito da tela. Como se trata de uma ferramenta *low-code*, você não precisa se preocupar em programar cada item: basta que você clique e arraste e o próprio Step Functions escreve o código em ASL (*Amazon State Language*), uma linguagem estruturada baseada em JSON. Cada "bloquinho" que você vê na visão de Design, que representa uma ação, é um bloco de código JSON.

Para criar, executar e ver funcionar o seu fluxo de trabalho, basta clicar no botão Criar, no topo direito da tela.

Como de praxe em muitos programas ao estilo estúdio, há as opções de desfazer e refazer ações.
Você também pode aumentar e diminuir o *zoom*, ou mesmo expor o fluxo inteiro no centro da tela.
Também é possível fazer configurações especifícas para uma ação no menu direito do estúdio, clicando em seu "bloquinho" antes.

**Após executar e estudar o seu projeto, é importantíssimo excluí-lo logo em seguida!**
Se você deixá-lo rodando, a Amazon vai entender que você está fazendo uso comercial dele, e vai te cobrar por isso.
Não há um preço fixo, pois você utiliza diversos serviços da AWS em seu projeto Step Functions, e cada serviço tem um preço.
E se dentro deste fluxo você utiliza um determinado serviço *x* vezes, o preço a ser pago é o deste serviço multiplicado por *x*.
Para auxiliar este cálculo, a própria AWS possui uma calculadora de preços, que te dá uma estimativa de quanto você vai pagar.
