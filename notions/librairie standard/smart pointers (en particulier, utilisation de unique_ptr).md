Les smart pointers sont des classes qui enveloppent un pointeur brut et qui s'occupent automatiquement de sa gestion de mémoire en libérant la mémoire allouée lorsque l'objet est détruit ou lorsqu'il n'est plus utilisé. L'un des smart pointers les plus couramment utilisés en C++ est std::unique_ptr.

Un std::unique_ptr est un pointeur intelligent qui possède la propriété exclusive de l'objet qu'il pointe. Cela signifie que lorsqu'un unique_ptr est détruit, l'objet pointé est également détruit. Les unique_ptr ne peuvent pas être copiés, mais peuvent être déplacés.

Voici un exemple d'utilisation d'un unique_ptr pour allouer dynamiquement un objet Person :

```cpp
#include <memory>
#include "Person.h"

int main() {
  std::unique_ptr<Person> p(new Person("John", "Doe", 25));
  p->sayHello();
  return 0;
}
```

Dans cet exemple, nous avons créé un objet Person en utilisant un unique_ptr. L'objet sera automatiquement détruit lorsque le unique_ptr sera détruit.

En général, il est recommandé d'utiliser des smart pointers pour éviter les fuites de mémoire et les erreurs de gestion de mémoire. Cependant, il est important de comprendre que les smart pointers ne sont pas une solution universelle pour la gestion de mémoire, et qu'il y a des situations où l'utilisation d'un pointeur brut est préférable.