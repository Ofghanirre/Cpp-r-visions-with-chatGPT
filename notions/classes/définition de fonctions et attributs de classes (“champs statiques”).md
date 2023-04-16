Les fonctions et attributs de classes, également appelés "membres statiques" ou "champs statiques", sont des éléments qui appartiennent à la classe elle-même plutôt qu'à une instance de la classe. Les membres statiques sont définis avec le mot-clé "static" devant leur déclaration.

Les fonctions membres statiques sont des fonctions qui n'ont pas accès à l'objet courant (this), car elles appartiennent à la classe plutôt qu'à une instance spécifique de la classe. Elles peuvent être appelées directement depuis la classe elle-même ou depuis une instance de la classe.

Exemple de définition d'une fonction membre statique :

```cpp
class Exemple {
public:
    static int compteur;
    static void incrementerCompteur() {
        compteur++;
    }
};

int Exemple::compteur = 0; // initialisation du compteur statique

int main() {
    Exemple::incrementerCompteur();
    Exemple e1;
    e1.incrementerCompteur();
    std::cout << "Compteur: " << Exemple::compteur << std::endl;
    return 0;
}
```

Dans cet exemple, la classe Exemple a un membre statique appelé "compteur", qui est initialisé à 0. La fonction membre statique "incrementerCompteur()" incrémente ce compteur à chaque appel. La fonction membre statique peut être appelée directement depuis la classe elle-même ou depuis une instance de la classe.

Les attributs de classe statiques sont des variables qui appartiennent à la classe elle-même plutôt qu'à une instance de la classe. Les attributs de classe statiques peuvent être utilisés pour stocker des informations qui s'appliquent à la classe dans son ensemble plutôt qu'à une instance spécifique de la classe.

Exemple de définition d'un attribut de classe statique :

```cpp
class Exemple {
public:
    static int compteur;
};

int Exemple::compteur = 0; // initialisation du compteur statique

int main() {
    Exemple::compteur++;
    Exemple e1;
    e1.compteur++;
    std::cout << "Compteur: " << Exemple::compteur << std::endl;
    return 0;
}
```

Dans cet exemple, la classe Exemple a un attribut de classe statique appelé "compteur", qui est initialisé à 0. L'attribut de classe statique peut être utilisé pour stocker des informations qui s'appliquent à la classe dans son ensemble plutôt qu'à une instance spécifique de la classe. L'attribut de classe statique peut être accédé directement depuis la classe elle-même ou depuis une instance de la classe.