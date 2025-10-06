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

