# Padrão de Projeto: Factory Method

## Contextualização Inicial
Em aplicações orientadas a objetos frequentemente temos código cliente que precisa criar objetos, mas a classe concreta do objeto só é conhecida em tempo de execução, por exemplo, dependendo da plataforma, do tipo de relatório, da configuração do usuário, etc. Se o cliente fizer new diretamente para todas as variantes, isso causa acoplamento forte, duplicação e dificuldade para estender o sistema.

O Factory Method organiza a criação de objetos delegando-a a métodos abstratos (ou protegidos) definidos em um Creator base; as subclasses implementam esse método para instanciar produtos concretos. Assim o cliente usa apenas o Creator (ou métodos dele), sem conhecer as classes concretas dos produtos.

## Definição do Padrão
Factory Method: Define uma interface para criar um objeto, mas deixa as subclasses decidirem qual classe instanciar. O método fábrica permite que uma classe adie a instanciação para subclasses.

Principais pontos:

* É um padrão criacional.
* Usa herança (subclasses sobrescrevem o factory method).
* Separa a criação do uso do objeto.

## Problema que resolve
Ele resolve o problema de acoplamento entre o código cliente e as classes concretas, permitindo que o sistema seja extensível sem modificações diretas. Ou seja, facilita a inclusão de novos tipos de objetos sem alterar o código existente apenas criando novas fábricas.
Esse padrão também:
* Evita if/else/switch espalhados pelo código para escolher qual classe criar.
* Reduz acoplamento entre cliente e classes concretas.
* Facilita adição de novos produtos: só crie uma nova ConcreteCreator e ConcreteProduct, sem alterar cliente.
* Ajuda a aderir ao princípio Open/Closed (abrir para extensão, fechar para modificação).

## Quando aplicar
Usar Factory Method quando:
* Quiser permitir que subclasses escolham qual classe de produto usar.
* O comportamento de criação precisa variar em subclasses.
* Uma classe não pode antecipar o tipo de objetos que deve criar.

Esse padrão pode ser aplicado em:
* Sistemas de pagamento internacional, onde a moeda varia conforme o país do cliente;
* Aplicativos de e-commerce, para formatar preços automaticamente;
* APIs que precisam retornar implementações específicas com base em configurações regionais.

## Representação UML


## Exemplo de Código

