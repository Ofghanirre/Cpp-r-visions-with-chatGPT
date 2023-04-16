La liaison statique et la liaison dynamique sont deux mécanismes qui permettent de déterminer quelle fonction membre d'une classe sera appelée lors de l'exécution d'un programme en C++.

La liaison statique est également appelée liaison précoce ou liaison compile-time. Elle se produit lors de la compilation du programme et consiste à résoudre les appels de fonctions en se basant sur le type statique des objets. Cela signifie que la fonction membre appelée est déterminée au moment de la compilation, en fonction du type déclaré de l'objet.

La liaison dynamique, quant à elle, est également appelée liaison tardive ou liaison runtime. Elle se produit lors de l'exécution du programme et consiste à résoudre les appels de fonctions en se basant sur le type dynamique des objets. Cela signifie que la fonction membre appelée est déterminée au moment de l'exécution, en fonction du type réel de l'objet.

La liaison dynamique est souvent utilisée lors de la mise en œuvre du polymorphisme en C++. Les fonctions membres virtuelles permettent de définir une interface commune pour un groupe de classes dérivées, tandis que les fonctions membres non virtuelles sont résolues de manière statique. Lorsqu'une fonction membre virtuelle est appelée via un pointeur ou une référence, la liaison se fait de manière dynamique.

Voici un exemple pour illustrer la différence entre la liaison statique et la liaison dynamique :

```cpp
#include <iostream>

class Forme {
public:
    void afficher() {
        std::cout << "Je suis une forme." << std::endl;
    }
    virtual void dessiner() {
        std::cout << "Je dessine une forme." << std::endl;
    }
};

class Rectangle : public Forme {
public:
    void afficher() {
        std::cout << "Je suis un rectangle." << std::endl;
    }
    void dessiner() {
        std::cout << "Je dessine un rectangle." << std::endl;
    }
};

int main() {
    Forme f;
    Rectangle r;

    Forme* pf = &f;
    pf->afficher(); // Appel à la fonction membre afficher() de Forme (liaison statique)
    pf->dessiner(); // Appel à la fonction membre dessiner() de Forme (liaison dynamique)

    pf = &r;
    pf->afficher(); // Appel à la fonction membre afficher() de Forme (liaison statique)
    pf->dessiner(); // Appel à la fonction membre dessiner() de Rectangle (liaison dynamique)

    return 0;
}
```

Dans cet exemple, la classe Forme a une fonction membre virtuelle dessiner(), tandis que la classe Rectangle redéfinit cette fonction. La fonction membre afficher() n'est pas virtuelle.

Lorsque la fonction membre afficher() est appelée via un pointeur de la classe de base Forme (pf), la liaison se fait de manière statique, car cette fonction n'est pas virtuelle. Cela signifie que la fonction membre afficher() de Forme sera appelée, même si pf pointe sur un objet de type Rectangle.

Ensuite, la fonction membre dessiner() est appelée via pf. Comme dessiner() est également une fonction virtuelle, la décision sur quelle fonction appeler est prise au moment de l'exécution, en fonction du type réel de l'objet pointé par pf. Dans ce cas, l'objet pointé est toujours de type Forme, mais comme la fonction dessiner() est redéfinie dans la classe Rectangle, la version de cette fonction dans la classe Rectangle est appelée.

Enfin, pf est réaffecté avec l'adresse de l'objet r. Comme r est un objet de type Rectangle, la fonction afficher() de la classe Forme est appelée car afficher() n'a pas été redéfinie dans la classe Rectangle. En revanche, la fonction dessiner() est appelée sur l'objet r, et comme cette fonction est redéfinie dans la classe Rectangle, la version de cette fonction dans la classe Rectangle est appelée.