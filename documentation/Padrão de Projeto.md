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
![Diagrama](https://drive.google.com/uc?export=view&id=1Mjh5z5_FLCHDqh6b9U1uo-yB-j03UjQa)

* Creator (Abstrata): Declara o método de fabricação (factoryMethod), que retorna um objeto do tipo Product. Também pode conter uma implementação padrão que utiliza o produto criado.
* ConcreteCreator (A e B): São as subclasses que implementam o factoryMethod para criar instâncias de produtos concretos (ConcreteProductA e ConcreteProductB).
* Product (Interface): Define a interface comum para os objetos que o método de fabricação cria.
* ConcreteProduct (A e B): São as classes que implementam a interface Product, representando os objetos que serão criados.

## Exemplo de Código
```
// Product
interface Notification {
    fun send(message: String)
}

// Concrete Products
class EmailNotification : Notification {
    override fun send(message: String) {
        println("Enviando e-mail: $message")
    }
}

class SMSNotification : Notification {
    override fun send(message: String) {
        println("Enviando SMS: $message")
    }
}

// Creator
abstract class NotificationCreator {
    abstract fun createNotification(): Notification

    fun notifyUser(message: String) {
        val notification = createNotification()
        notification.send(message)
    }
}

// Concrete Creators
class EmailNotificationCreator : NotificationCreator() {
    override fun createNotification(): Notification = EmailNotification()
}

class SMSNotificationCreator : NotificationCreator() {
    override fun createNotification(): Notification = SMSNotification()
}

// Client
fun main() {
    val creator: NotificationCreator = EmailNotificationCreator()
    creator.notifyUser("Bem-vindo!")

    val smsCreator: NotificationCreator = SMSNotificationCreator()
    smsCreator.notifyUser("Código de verificação: 1234")
}
```
### Product
```
interface Notification {
    fun send(message: String)
}
```
* Notification é a interface do produto.
* Define o comportamento que todos os tipos de notificação devem ter (send).

### Concrete Products
```
class EmailNotification : Notification {
    override fun send(message: String) {
        println("Enviando e-mail: $message")
    }
}

class SMSNotification : Notification {
    override fun send(message: String) {
        println("Enviando SMS: $message")
    }
}
```
* EmailNotification e SMSNotification são os produtos concretos.
* Eles implementam a interface Notification com comportamentos específicos.

### Creator
```
abstract class NotificationCreator {
    abstract fun createNotification(): Notification

    fun notifyUser(message: String) {
        val notification = createNotification()
        notification.send(message)
    }
}
```
* NotificationCreator é a classe criadora abstrata.
* Define o método Factory: createNotification().
* Tem um método notifyUser que usa o produto retornado pelo Factory Method.

Ponto chave: o creator não sabe qual produto específico será criado, isso é decidido pelas subclasses.

### Concrete Creators
```
class EmailNotificationCreator : NotificationCreator() {
    override fun createNotification(): Notification = EmailNotification()
}

class SMSNotificationCreator : NotificationCreator() {
    override fun createNotification(): Notification = SMSNotification()
}
```
* Subclasses concretas do creator que decidem qual produto criar.
* EmailNotificationCreator cria EmailNotification, e SMSNotificationCreator cria SMSNotification.

### Client
```
fun main() {
    val creator: NotificationCreator = EmailNotificationCreator()
    creator.notifyUser("Bem-vindo!")

    val smsCreator: NotificationCreator = SMSNotificationCreator()
    smsCreator.notifyUser("Código de verificação: 1234")
}
```
* O client usa o creator abstrato, mas pode passar qualquer Concrete Creator.
* Não precisa instanciar diretamente EmailNotification ou SMSNotification.
* Fácil adicionar novos tipos de notificações sem alterar o código do client.
