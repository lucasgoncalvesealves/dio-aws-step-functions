# Criando um Assistente de Delivery com AWS Step Functions e Bedrock

Um aplicativo de smartphone pode ser um monolito (uma única aplicação) ou dividido em microsserviços.

Por exemplo, um aplicativo de entrega de comida é composto de:
1. Uma API de gerenciamento de usuários;
2. Um gerenciador de notificações *push*;
3. Uma API de gerenciamento de estado do pedido.

Existe um **fluxo** entre os microsserviços, ou seja, um depende do outro.
