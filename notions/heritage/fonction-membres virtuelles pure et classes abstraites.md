En C++, une fonction membre virtuelle pure est une fonction membre virtuelle déclarée dans une classe de base, mais qui n'a pas de définition. Elle est déclarée en utilisant la syntaxe suivante :

```cpp
virtual type_de_retour nom_de_la_fonction(paramètres) = 0;
```

Le = 0 à la fin de la déclaration indique que la fonction est virtuelle pure.

Une classe contenant au moins une fonction membre virtuelle pure est appelée une classe abstraite. Une classe abstraite ne peut pas être instanciée directement ; elle ne peut être utilisée que comme classe de base pour d'autres classes qui la redéfinissent.

Voici un exemple pour illustrer cela :

```cpp
class Forme {
public:
    virtual void dessiner() = 0;
};

class Rectangle : public Forme {
public:
    void dessiner() {
        cout << "Je suis un rectangle." << endl;
    }
};

class Cercle : public Forme {
public:
    void dessiner() {
        cout << "Je suis un cercle." << endl;
    }
};

int main() {
    // Forme* f = new Forme(); // Erreur : impossible d'instancier une classe abstraite
    Forme* f1 = new Rectangle();
    Forme* f2 = new Cercle();
    f1->dessiner(); // Appel de la fonction dessiner() de Rectangle
    f2->dessiner(); // Appel de la fonction dessiner() de Cercle
    return 0;
}
```

Dans cet exemple, la classe de base Forme a une fonction membre virtuelle pure dessiner(), ce qui en fait une classe abstraite. Les classes dérivées Rectangle et Cercle redéfinissent cette fonction pour dessiner des formes spécifiques.

Lors de l'exécution, il est possible d'instancier des objets de la classe dérivée (Rectangle et Cercle) via un pointeur de la classe de base (Forme). Cependant, il est impossible d'instancier directement un objet de la classe abstraite Forme.

Les classes abstraites sont souvent utilisées pour définir une interface commune à un groupe de classes qui partagent des caractéristiques similaires. Les fonctions membres virtuelles pures définissent une interface commune pour ces classes, tandis que les classes dérivées fournissent l'implémentation spécifique à chaque classe.