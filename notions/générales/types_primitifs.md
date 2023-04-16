En C++, les types primitifs représentent des données de base qui sont utilisées pour stocker des valeurs simples telles que des entiers, des nombres flottants, des caractères et des booléens. Voici les types primitifs de base en C++ :

- int : entier signé, pouvant représenter des valeurs de -2^31 à 2^31-1 sur des architectures 32 bits ou de -2^63 à 2^63-1 sur des architectures 64 bits.
- unsigned int : entier non signé, pouvant représenter des valeurs de 0 à 2^32-1 sur des architectures 32 bits ou de 0 à 2^64-1 sur des architectures 64 bits.
- short : entier signé de petite taille, pouvant représenter des valeurs de -2^15 à 2^15-1.
- unsigned short : entier non signé de petite taille, pouvant représenter des valeurs de 0 à 2^16-1.
- long : entier signé de grande taille, pouvant représenter des valeurs de -2^31 à 2^31-1 sur des architectures 32 bits ou de -2^63 à 2^63-1 sur des architectures 64 bits.
- unsigned long : entier non signé de grande taille, pouvant représenter des valeurs de 0 à 2^32-1 sur des architectures 32 bits ou de 0 à 2^64-1 sur des architectures 64 bits.
- char : caractère de 8 bits, pouvant représenter des valeurs de -128 à 127 ou de 0 à 255 en fonction de la représentation signée ou non signée.
- bool : booléen, pouvant prendre les valeurs true ou false.
- float : nombre à virgule flottante de 32 bits.
- double : nombre à virgule flottante de 64 bits.
Voici un exemple simple qui illustre la déclaration et l'initialisation de variables de différents types primitifs :

```cpp
#include <iostream>

int main()
{
    int myInt = 42;
    unsigned int myUInt = 1234567890;
    short myShort = -32768;
    unsigned short myUShort = 65535;
    long myLong = 123456789012345;
    unsigned long myULong = 987654321098765;
    char myChar = 'a';
    bool myBool = true;
    float myFloat = 3.14f;
    double myDouble = 3.141592653589793;

    std::cout << "int : " << myInt << std::endl;
    std::cout << "unsigned int : " << myUInt << std::endl;
    std::cout << "short : " << myShort << std::endl;
    std::cout << "unsigned short : " << myUShort << std::endl;
    std::cout << "long : " << myLong << std::endl;
    std::cout << "unsigned long : " << myULong << std::endl;
    std::cout << "char : " << myChar << std::endl;
    std::cout << "bool : " << myBool << std::endl;
    std::cout << "float : " << myFloat << std::endl;
    std::cout << "double : " << myDouble << std::endl;

    return 0;
}
```
