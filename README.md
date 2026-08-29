<p align="center">
  <img src="images/poo 02.png" alt="Programação Orientada a Objetos com Java">
</p>

# ☕ Orientação a Objetos em Java: Entendendo os Fundamentos da POO

> Um guia prático para entender os principais conceitos da Programação Orientada a Objetos utilizando Java.

---

## 📌 Introdução

Quando começamos a estudar Java, um dos conceitos mais importantes que encontramos é a **Programação Orientada a Objetos (POO)**.

No início, termos como **classe, objeto, atributo, método, construtor, encapsulamento, herança e polimorfismo** podem parecer complicados.

Mas existe uma ideia simples por trás de tudo:

> **A Programação Orientada a Objetos organiza o código utilizando objetos que possuem características e comportamentos.**

Em vez de pensar apenas em funções e dados separados, passamos a representar elementos do mundo real dentro do programa.

Por exemplo:

* Uma pessoa possui **nome, idade e endereço**.
* Um carro possui **marca, modelo e velocidade**.
* Uma conta bancária possui **saldo e número da conta**.
* Um funcionário possui **nome, salário e cargo**.

Essas características e comportamentos podem ser representados através de classes e objetos.

---

# 🧠 O que é Programação Orientada a Objetos?

A **Programação Orientada a Objetos**, conhecida como **POO**, é um paradigma de programação baseado na utilização de **objetos**.

Um objeto pode representar alguma coisa do mundo real ou um conceito dentro do sistema.

Por exemplo:

```text
Pessoa
 ├── nome
 ├── idade
 └── endereço

Métodos:
 ├── apresentar()
 └── fazerAniversario()
```

Nesse exemplo:

* `nome`, `idade` e `endereço` são **atributos**;
* `apresentar()` e `fazerAniversario()` são **métodos**.

A POO permite reunir esses dados e comportamentos em uma estrutura chamada **classe**.

---

# 🏗️ Classe

Uma **classe** funciona como um modelo ou projeto para criação de objetos.

Imagine uma planta de uma casa.

A planta não é a casa propriamente dita. Ela é o modelo utilizado para construir a casa.

Da mesma maneira:

```java
public class Pessoa {

    String nome;
    int idade;

}
```

A classe `Pessoa` define quais características uma pessoa terá.

Podemos criar objetos a partir dessa classe:

```java
Pessoa pessoa1 = new Pessoa();
Pessoa pessoa2 = new Pessoa();
```

Agora temos dois objetos diferentes utilizando o mesmo modelo.

---

# 📦 Objeto

O **objeto** é uma instância de uma classe.

Podemos pensar assim:

```text
CLASSE
   ↓
  Pessoa
   ↓
   ├── pessoa1
   ├── pessoa2
   └── pessoa3
```

Cada objeto pode possuir seus próprios valores.

```java
Pessoa pessoa1 = new Pessoa();

pessoa1.nome = "Carlos";
pessoa1.idade = 30;
```

Outro objeto pode possuir valores diferentes:

```java
Pessoa pessoa2 = new Pessoa();

pessoa2.nome = "Ana";
pessoa2.idade = 25;
```

Embora os dois objetos sejam criados a partir da mesma classe, cada um possui seu próprio estado.

---

# 🔹 Atributos

Os **atributos** representam as características ou o estado de um objeto.

Exemplo:

```java
public class Carro {

    String marca;
    String modelo;
    int ano;

}
```

Nesse caso temos três atributos:

```text
marca
modelo
ano
```

Podemos criar um objeto:

```java
Carro carro = new Carro();

carro.marca = "Toyota";
carro.modelo = "Corolla";
carro.ano = 2025;
```

Agora o objeto `carro` possui um estado definido.

---

# ⚙️ Métodos

Os **métodos** representam comportamentos ou ações que um objeto pode realizar.

Exemplo:

```java
public class Carro {

    String marca;
    String modelo;

    void acelerar() {
        System.out.println("O carro está acelerando!");
    }

}
```

Podemos utilizar:

```java
Carro carro = new Carro();

carro.acelerar();
```

Resultado:

```text
O carro está acelerando!
```

Portanto:

> **Atributos representam características. Métodos representam comportamentos.**

---

# 🏗️ Construtores

O **construtor** é utilizado para inicializar um objeto no momento em que ele é criado.

Exemplo:

```java
public class Pessoa {

    String nome;
    int idade;

    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

Agora podemos criar o objeto já informando seus dados:

```java
Pessoa pessoa = new Pessoa("Carlos", 30);
```

O construtor recebe:

```text
"Carlos"
30
```

e inicializa os atributos do objeto.

---

# 🔑 Palavra-chave `this`

A palavra-chave `this` representa o **objeto atual**.

Veja:

```java
public Pessoa(String nome, int idade) {
    this.nome = nome;
    this.idade = idade;
}
```

Temos dois `nome`:

```java
this.nome
```

representa o atributo da classe.

Já:

```java
nome
```

representa o parâmetro recebido pelo construtor.

Podemos interpretar:

```text
this.nome = nome;
   ↑         ↑
atributo   parâmetro
```

---

# 🔐 Encapsulamento

O **encapsulamento** é um dos principais conceitos da POO.

Ele consiste em proteger o estado interno do objeto e controlar como seus dados podem ser acessados ou modificados.

Em Java, normalmente utilizamos:

```java
private
```

para proteger os atributos.

Exemplo:

```java
public class Conta {

    private double saldo;

}
```

Agora o atributo `saldo` não pode ser acessado diretamente de qualquer lugar.

Podemos criar métodos para controlar o acesso:

```java
public class Conta {

    private double saldo;

    public double getSaldo() {
        return saldo;
    }

    public void depositar(double valor) {
        if (valor > 0) {
            saldo += valor;
        }
    }
}
```

Utilização:

```java
Conta conta = new Conta();

conta.depositar(500);

System.out.println(conta.getSaldo());
```

Resultado:

```text
500.0
```

Isso permite criar regras para proteger os dados.

---

# 🧱 Os 4 pilares da POO

A Programação Orientada a Objetos possui quatro conceitos fundamentais:

```text
        POO
         │
 ┌───────┼────────┐
 │       │        │
Encap.  Herança  Polimorfismo
 │
Abstração
```

Os quatro pilares são:

1. **Encapsulamento**
2. **Herança**
3. **Polimorfismo**
4. **Abstração**

Vamos entender cada um deles.

---

# 🔐 1. Encapsulamento

O encapsulamento protege os dados internos de um objeto.

Exemplo:

```java
public class Usuario {

    private String nome;

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}
```

O atributo:

```java
private String nome;
```

não pode ser acessado diretamente fora da classe.

Utilizamos métodos para controlar o acesso:

```java
usuario.setNome("Carlos");

System.out.println(usuario.getNome());
```

O encapsulamento ajuda a:

* proteger os dados;
* controlar alterações;
* aplicar regras de negócio;
* reduzir o acoplamento;
* melhorar a manutenção do código.

---

# 🧬 2. Herança

A **herança** permite que uma classe aproveite características e comportamentos de outra classe.

Imagine:

```text
             Animal
               │
       ┌───────┴───────┐
       │               │
      Cachorro        Gato
```

Podemos criar:

```java
public class Animal {

    void emitirSom() {
        System.out.println("Animal emitindo som");
    }
}
```

Depois:

```java
public class Cachorro extends Animal {

}
```

A classe `Cachorro` herda características e comportamentos de `Animal`.

Podemos utilizar:

```java
Cachorro cachorro = new Cachorro();

cachorro.emitirSom();
```

A palavra-chave utilizada para herança é:

```java
extends
```

---

# 🔄 3. Polimorfismo

A palavra **polimorfismo** significa "muitas formas".

Na prática, permite que objetos diferentes sejam tratados através de um tipo comum, mas apresentem comportamentos diferentes.

Exemplo:

```java
public class Animal {

    void emitirSom() {
        System.out.println("Som do animal");
    }
}
```

Cachorro:

```java
public class Cachorro extends Animal {

    @Override
    void emitirSom() {
        System.out.println("Au au!");
    }
}
```

Gato:

```java
public class Gato extends Animal {

    @Override
    void emitirSom() {
        System.out.println("Miau!");
    }
}
```

Agora:

```java
Animal animal1 = new Cachorro();
Animal animal2 = new Gato();

animal1.emitirSom();
animal2.emitirSom();
```

Resultado:

```text
Au au!
Miau!
```

Embora as variáveis sejam do tipo `Animal`, cada objeto apresenta seu próprio comportamento.

---

# 🧩 4. Abstração

A **abstração** consiste em representar apenas aquilo que é relevante para determinado contexto, escondendo detalhes desnecessários.

Imagine um sistema bancário.

O usuário precisa saber que pode:

```text
Depositar
Sacar
Consultar saldo
Transferir
```

Ele não precisa conhecer todos os detalhes internos de implementação dessas operações.

Em Java podemos utilizar classes abstratas:

```java
public abstract class Animal {

    public abstract void emitirSom();

}
```

Uma classe filha pode implementar esse comportamento:

```java
public class Cachorro extends Animal {

    @Override
    public void emitirSom() {
        System.out.println("Au au!");
    }
}
```

A abstração ajuda a definir **o que deve ser feito**, deixando para as classes concretas a responsabilidade de definir **como será feito**.

---

# 🧩 Interface

Outro recurso muito importante em Java é a **interface**.

Uma interface pode definir um contrato que uma classe deve seguir.

Exemplo:

```java
public interface Pagamento {

    void pagar();

}
```

Uma classe pode implementar essa interface:

```java
public class Pix implements Pagamento {

    @Override
    public void pagar() {
        System.out.println("Pagamento realizado via Pix.");
    }
}
```

Outra classe:

```java
public class Cartao implements Pagamento {

    @Override
    public void pagar() {
        System.out.println("Pagamento realizado via cartão.");
    }
}
```

Podemos então trabalhar com o mesmo contrato:

```java
Pagamento pagamento = new Pix();

pagamento.pagar();
```

Isso torna o sistema mais flexível e facilita a substituição de implementações.

---

# 🆚 Classe x Objeto

Uma dúvida muito comum de quem está começando:

### Classe

É o modelo.

```java
public class Pessoa {

    String nome;
    int idade;

}
```

### Objeto

É uma instância da classe.

```java
Pessoa pessoa = new Pessoa();
```

Podemos resumir:

```text
Classe = modelo

Objeto = instância do modelo
```

Uma analogia simples:

```text
Classe
   ↓
Planta de uma casa
   ↓
Objetos
   ↓
Casas construídas
```

---

# 🏦 Exemplo prático: Conta Bancária

Vamos juntar vários conceitos da POO em um exemplo simples.

```java
public class Conta {

    private String titular;
    private double saldo;

    public Conta(String titular, double saldoInicial) {
        this.titular = titular;
        this.saldo = saldoInicial;
    }

    public void depositar(double valor) {

        if (valor > 0) {
            saldo += valor;
        }
    }

    public boolean sacar(double valor) {

        if (valor > 0 && valor <= saldo) {
            saldo -= valor;
            return true;
        }

        return false;
    }

    public double getSaldo() {
        return saldo;
    }

    public String getTitular() {
        return titular;
    }
}
```

Podemos utilizar:

```java
public class Main {

    public static void main(String[] args) {

        Conta conta = new Conta("Carlos", 500);

        conta.depositar(200);

        conta.sacar(100);

        System.out.println("Titular: " + conta.getTitular());
        System.out.println("Saldo: " + conta.getSaldo());
    }
}
```

Resultado:

```text
Titular: Carlos
Saldo: 600.0
```

Nesse pequeno exemplo utilizamos:

* Classe
* Objeto
* Atributos
* Métodos
* Construtor
* `this`
* Encapsulamento
* `private`
* `public`
* Validação de dados

---

# 🧠 Como pensar em POO

Uma boa forma de aprender POO é transformar um problema em perguntas.

Imagine um sistema de biblioteca.

Pergunte:

### Quais são os objetos?

```text
Livro
Aluno
Bibliotecário
Empréstimo
```

### Quais são suas características?

```text
Livro
 ├── título
 ├── autor
 └── ISBN
```

### Quais são seus comportamentos?

```text
Livro
 ├── emprestar()
 └── devolver()
```

Depois podemos transformar isso em classes Java.

```java
public class Livro {

    private String titulo;
    private String autor;
    private String isbn;

    public void emprestar() {
        System.out.println("Livro emprestado.");
    }

    public void devolver() {
        System.out.println("Livro devolvido.");
    }
}
```

Esse processo de identificar **objetos, características e comportamentos** é uma das melhores formas de começar a pensar orientado a objetos.

---

# 🗺️ Mapa mental da POO

```text
                 PROGRAMAÇÃO
                ORIENTADA A
                  OBJETOS
                      │
        ┌─────────────┼─────────────┐
        │             │             │
      CLASSE        OBJETO       MÉTODO
        │             │             │
    ┌───┴───┐         │        Comportamento
    │       │         │
Atributos Métodos     │
                       │
                  Instância
                       │
              ┌────────┴────────┐
              │                 │
        Encapsulamento      Abstração
              │                 │
           Herança        Polimorfismo
```

---

# 🚀 Por que aprender POO?

A Programação Orientada a Objetos é muito utilizada porque ajuda a construir sistemas maiores e mais organizados.

Entre seus benefícios estão:

✅ Organização do código
✅ Reutilização de código
✅ Manutenção mais simples
✅ Separação de responsabilidades
✅ Maior segurança dos dados
✅ Facilidade para evolução do sistema
✅ Redução de código duplicado
✅ Melhor representação de problemas complexos

Por isso, compreender POO é fundamental para quem deseja evoluir no desenvolvimento Java.

---

# ☕ Java e Orientação a Objetos

Java foi projetado com forte utilização do paradigma orientado a objetos.

Durante o desenvolvimento em Java, encontramos constantemente conceitos como:

```text
Class
Object
Constructor
Method
Encapsulation
Inheritance
Polymorphism
Abstraction
Interface
```

Por isso, dominar esses conceitos não significa apenas aprender algumas palavras-chave.

Significa aprender uma nova maneira de **pensar e estruturar soluções de software**.

---

# 🎯 O que estudar depois?

Depois de compreender os fundamentos, vale aprofundar nos seguintes assuntos:

```text
POO
│
├── Classes e Objetos
├── Atributos
├── Métodos
├── Construtores
├── this
├── Encapsulamento
│   ├── private
│   ├── public
│   ├── getters
│   └── setters
│
├── Herança
│   ├── extends
│   └── super
│
├── Polimorfismo
│   └── @Override
│
├── Abstração
│   ├── abstract
│   └── interfaces
│
└── Relacionamento entre objetos
    ├── Associação
    ├── Agregação
    └── Composição
```

---

# 💡 Conclusão

Aprender Orientação a Objetos é muito mais do que decorar definições.

O verdadeiro aprendizado acontece quando conseguimos olhar para um problema e identificar:

> **Quais são os objetos? Quais são suas características? Quais comportamentos eles possuem? E como esses objetos se relacionam?**

A partir daí, conceitos como **classes, objetos, encapsulamento, herança, polimorfismo e abstração** começam a fazer sentido.

No início, POO pode parecer complexa. Mas, com prática, esses conceitos passam a fazer parte da forma como pensamos na construção de sistemas.

Para quem está aprendendo Java, dominar POO é um dos passos mais importantes para sair de programas simples e começar a construir aplicações realmente estruturadas.

---

## 📚 Resumo rápido

| Conceito           | Significado                                                |
| ------------------ | ---------------------------------------------------------- |
| **Classe**         | Modelo para criação de objetos                             |
| **Objeto**         | Instância de uma classe                                    |
| **Atributo**       | Característica/estado do objeto                            |
| **Método**         | Comportamento/ação do objeto                               |
| **Construtor**     | Inicializa o objeto                                        |
| **Encapsulamento** | Protege e controla os dados                                |
| **Herança**        | Permite reutilizar características e comportamentos        |
| **Polimorfismo**   | Permite diferentes comportamentos através de um mesmo tipo |
| **Abstração**      | Esconde detalhes e expõe o que é relevante                 |
| **Interface**      | Define um contrato que classes podem implementar           |

---

## 👨‍💻 Na prática

A melhor maneira de aprender POO é **praticando**.

Comece com classes simples:

```text
Pessoa
Produto
Carro
Conta
Aluno
Livro
Funcionario
```

Depois evolua para sistemas pequenos:

```text
🏦 Sistema Bancário
📚 Sistema de Biblioteca
🛒 Sistema de Produtos
🎓 Sistema Escolar
🚗 Sistema de Veículos
```

Cada novo projeto será uma oportunidade para aplicar os conceitos de POO e entender como eles funcionam na prática.

---

### 🚀 Continue estudando!

> **Escrever código é aprender a programar.
> Entender objetos é aprender a projetar sistemas.**

☕ **Java + POO + prática = evolução constante.**

---

**#Java #Programacao #POO #OrientacaoAObjetos #DIO #DesenvolvimentoDeSoftware #Tecnologia #DesenvolvimentoJava #ProgramacaoOrientadaAObjetos**
