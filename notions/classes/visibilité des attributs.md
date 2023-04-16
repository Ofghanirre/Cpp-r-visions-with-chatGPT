En C++, la visibilité des attributs d'une classe est contrôlée à l'aide de l'un des trois modificateurs d'accès : "public", "private" et "protected".

Les attributs déclarés dans la section "public" sont accessibles à partir de n'importe quelle fonction ou instance de la classe, ainsi que depuis des fonctions et des classes extérieures.

Les attributs déclarés dans la section "private" sont uniquement accessibles à partir des fonctions membres de la classe. Les fonctions et classes extérieures ne peuvent pas accéder directement à ces attributs.

Les attributs déclarés dans la section "protected" sont similaires à ceux déclarés en privé, à la différence que les classes dérivées de la classe qui les contient peuvent accéder à ces attributs.

Voici un exemple pour illustrer cela :

```cpp
class Exemple {
public:
    int publicAttr;
private:
    int privateAttr;
protected:
    int protectedAttr;
};

int main() {
    Exemple e;
    e.publicAttr = 1; // OK
    e.privateAttr = 2; // Erreur de compilation
    e.protectedAttr = 3; // Erreur de compilation
    return 0;
}
```

Dans cet exemple, la classe Exemple contient trois attributs : un attribut public, un attribut privé et un attribut protégé. La tentative d'accéder aux attributs privé et protégé depuis la fonction principale provoque une erreur de compilation.

En général, il est recommandé de déclarer les attributs comme privés et de fournir des fonctions membres publiques pour y accéder ou les modifier. Cela permet de contrôler l'accès aux données de la classe et de mieux encapsuler les fonctionnalités de la classe.