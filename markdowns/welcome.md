# Welcome!

Primeiro Hello World com Dart
```dart runnable
void main() {
    print("Hello world");
}

```

# Aula 1

### Variáveis e constantes
Dart é uma linguagem fortemente tipada
As variáveis podem ser um ou mais caracteres, números inteiros ou de ponto flutuante e booleanos como verdadeiro e falso.

```dart runnable
void main() {
    
    String myString = "Hello World";
    int myNumber = 2;
    double myFloat = 2.5;
    bool myBool;
    var myVar = 1;

    print(myString);
}
```

Constantes são variáveis que teráo seus valores fixos independente do tempo de compilação, ou seja não poderá ter seu valor mudado.  
Observe que o código abaixo irá falar, pois tentei mudar o valor de myFloat mesmo ele sendo uma constante.

```dart runnable
void main() {
    
    const String myString = "Hello World";
    const int myNumber = 2;
    const double myFloat = 2.5;
    myFloat = 2.6;
    var myVar = 1;

    print(myString);
}
```

Além do "const" temos o "final", que trata uma variável como constante em tempo de compilação, antes do seu valor ser conhecido.
o código abaixo não irá funcionar, pois estamos entrando com dados e o tech.io não é adequado para isso, copie e cole o techo desejado no replit.

```dart runnable
import 'dart:io';
void main() {
    
    const String myString = "Hello World";
    const int myNumber = 2;
    const double myFloat = 2.5;
    final entradaDoUsuario = stdin.readLineSync();
    myFloat = 2.6;
    var myVar = 1;

    print(entradaDoUsuario);
}
```

Em dart é possível efetuar operações tambem.

```dart runnable
void main() {
    
    const String myString = "Hello World";
    const int myNumber = 2;
    const double myFloat = 2.5;
   
    var myNewVar = myNumber + myFloat;

    print(myNewVar);
    print(myNumber * 2);
}
```

É difícil de acontecer, mas caso exista alguma variável que não saibamos o tipo, basta usar o método runtimeType.

```dart runnable
void main() {
    
    const String myString = "Hello World";
    var myVar = "Outra string";
    
    print(myVar.runtimeType);
}

```

Em dart existem alguns métodos interessantes de se conhecer além do runtimeType. 
São eles roundToDouble(), substring(arg0*, arg1*), toUpperCase(), abs()
```dart runnable
void main() {
    
    const String myString = "Hello World";
    double myDouble = 2.5987;
    var myVar = "Outra string";
    

    print(myVar);
    print(myVar.toUpperCase());
    print(myVar.substring(0, 4));
    print(myDouble.roundToDouble());
    print(myDouble.abs());
}
```

Vamos falar agora sobre operadores. Eles podem ser aritméticos ou lógicos.

abaixo temos um exemplo de operadores aritméticos
```dart runnable
void main() {
    
    int x = 7;
    int y = 3;
    int resultado = x + y;
    print(resultado);
    print(x * y);
    print(x - y);
    print(x / y);
    print(x % y);
}
```

abaixo temos um exemplo de operadores lógicos
```dart runnable
void main() {
    
    bool fragil = true;
    bool caro = false;

    print(fragil && caro);
    print(fragil || caro);
    print(fragil ^ caro);
    print(!fragil);

    print(3<2);
    print(3 == 2);
    print(2 == 2);
    print(2 <= 5);
}
```
### Entrada de dados
Algumas vezes pode ser preciso capturar os dados do usuário. Para tal, faremos da forma abaixo.
```dart runnable
import 'dart:io';

void main() {
    
    print("Está chovendo? (s/N)");
    String? estaChovendo = stdin.readLineSync();

}
```
o comando não irá rodar pois estamos executando na forma de snippets, mas pelo replit será mais fácil rodar.

### Nullsafety
Em dart, quando o usuário irá executar a entrada de dados precisamos executar a verificação nula.
Colocando um "?" após a tipagem, antes do nome da variável, como no exemplo supracitado, porém podemos querer fazer essa verificação ao declararmos variáveis.
Caso queira garantir que determinada variável não será nula atribua "!" após a sua captura de dados.
```dart runnable
void main() {
    
   String? myString;
   int? myInt;

   myInt = 2;
   print(myInt);

}
```

```dart runnable
void main() {
    
   String? myString;
   int? myInt;

   myInt = 2;
   print("myInt = $myInt");
   print(myString);
}
```

```dart runnable
import 'dart:io';
 
void main()
{
    
    print("Enter first number");
    int? n1 = int.parse(stdin.readLineSync()!);
 
    print("Enter second number");
    int? n2 = int.parse(stdin.readLineSync()!);
 
    int sum = n1 + n2;
    print("Sum is $sum");
}
```
### Estruturas de controle
Estruturas de controle são artifícios das linguagens de programação para determinar qual bloco de código será executado a partir de uma determinada condição. No Dart, assim como em outras linguagens, podemos trabalhar com as estruturas de condição utilizando o if/else e o switch/case como veremos abaixo.

if/else

Como o próprio nome já diz, se(if) a condicional for verdadeira, irá executar aquele trecho e caso náo seja irá executar o else, de acordo com os exemplos abaixo 
```dart runnable
void main() {
  var idade = 18;
  if (idade < 18) {
    print("Você é menor de idade");
  }
}
```
```dart runnable
void main() {
  var idade = 18;
  if (idade < 18) {
    print("Você é menor de idade");
  } else {
    print("Você é maior de idade");
  }
}
```

Além do if/else temos o swicth/case que é semelhante a primeira estrutura supracitada, porém mais elegante.

```dart runnable
void main() {
  var opcao = 2;
  switch (opcao) {
      case 1:
        print("Cadastrar");
        break;
      case 2:
        print("Listar");
        break;
      default:
        print("Sair");
    }
}
```
### Estruturas de repetição
Estruturas de repetição são artifícios das linguagens de programação para executar um determinado bloco de código por uma certa quantidade de vezes, seja ela definida (utilizando o for) ou a partir de uma condição (utilizando o while).

for
A estrutura de repetição "for" executará um determinado bloco de código por um número definido de vezes. 

```dart runnable
void main() {
  for (int numero = 1; numero <= 10; numero++){
    if (numero % 2 == 0) {
      print(numero);
    }
  }
}
```

while
O while é uma estrutura de repetição que permite executar um determinado bloco de código enquanto uma condição for verdadeira. É muito similar ao if, com a diferença que o bloco será executado enquanto a condição for verdadeira, e não se a condição for verdadeira.

```dart runnable
void main() {
  var numero = 1;

  while (numero <= 10) {
    if (numero % 2 == 0) {
      print(numero);
    }
  numero++;
  }
}
```
do/while
```dart runnable
void main() {
  var numero = 1;
  
   do {
    if (numero % 2 == 0) {
      print(numero);
    }
    numero++;
  } while (numero <= 10);
}
```

### Coleções em dart
Coleções são tidas como estruturas de dados, alguns exemplos delas são: Listas, Maps e Sets.

Listas

Listas como o próprio nome diz são um conjunto de elementos ordenados por um índice.
```dart runnable
void main() {
    
    List lista = ['Brazil', 'Argentina', 'Argélia'];
    
    
    print(lista);
    print(lista[0]);
}
```

Para adicionar elementos em uma lista utiliza-se a função .add(), de acordo com o exemplo abaixo.
```dart runnable
void main() {
    
    List lista = ['Brazil', 'Argentina', 'Argélia'];
    lista.add('China');
    
    print(lista);
}
```

Para remover elementos de uma lista pelo índice utiliza-se a função .removeAt(), de acordo com o exemplo abaixo.
```dart runnable
void main() {
    
    List lista = ['Brazil', 'Argentina', 'Argélia'];
    lista.removeAt(0);
    
    print(lista);
}
```

Para remover elementos de uma lista pelo nome utiliza-se a função .remove(), de acordo com o exemplo abaixo.
```dart runnable
void main() {
    
    List lista = ['Brazil', 'Argentina', 'Argélia'];
    lista.remove('Brazil');
    
    print(lista);
}
```

Para inverter elementos de uma lista utiliza-se a função .reversed, de acordo com o exemplo abaixo.
```dart runnable
void main() {
    
    List lista = ['Brazil', 'Argentina', 'Argélia'];
    
    print(lista.reversed);
}
```

Sets
Os Sets são definidos como uma coleção não ordenada de objetos únicos. Para definir um conjunto siga o seguinte:
Sets armazenam um grupo de objetos que não se repetem. As mesmas operações das listas estão disponíveis para eles.

```dart runnable
void main() {
    
    Set fruits = Set.from("Mango", "Apple", "Banana");
    
    print(fruits);
}
```

Maps ou JSON
No Dart, os maps são coleções não ordenadas de pares de valores-chave que definem uma chave associada para os valores contidos. Para definir um mapa, especifique o tipo de chave e o tipo de valor dentro dos colchetes angulares (<>) conforme mostrado abaixo:

```dart runnable
void main() {
    
    Map<int, String> fruits = {1: "Mango", 2:"Apple", 3:"Banana"};
    print(fruits);
    print('Keys: ${fruits.keys} \nValues: ${fruits.values}');
    print('{$fruits} length is ${fruits.length}');

}
```

Generics
Em dart generics é algo amplamente utilizado quando lidamos com estruturas de dados como listas, maps, etc.

```dart runnable
void main() {
    
    List<int> fruits = [1,2,3,4,5];
    print(fruits);
}
```

No exemplo abaixo o código não irá rodar, pois temos um elemento dentro da nossa lista de inteiros que é uma string e essa é a função do nosso generics "<>"
```dart runnable
void main() {
    
    List<int> fruits = [1,2,3,4,5, '1'];
    print(fruits);
}
```
Isso pode ser aplicado para quaisquer estruturas. além de tipar a variável, caso ela seja uma estrutura tipamos seus elementos.