# Criando um Assistente de Delivery com AWS Step Functions e Bedrock

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

Para acessá-lo a partir da página inicial, vá em Serviços --> Integração de Aplicativos --> Step Functions
