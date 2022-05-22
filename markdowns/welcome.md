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

Constantes são variáveis que teráo seus valores fixos, ou seja não poderá ter seu valor mudado.  
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

```dart runnable
import 'dart:io';
void main() {
    
   String? myString;
   int? myInt;

   myInt = 2;
   print(myInt);

}
```

```dart runnable
import 'dart:io';
void main() {
    
   String? myString;
   int? myInt;

   myInt = 2;
   print(myInt);
   print(myString);
}
```

### Coleções em dart

```dart runnable
void main() {
    
    const String myString = "Hello World";
    var myVar = "Outra string";
    
    print(myVar.runtimeType);
}
```