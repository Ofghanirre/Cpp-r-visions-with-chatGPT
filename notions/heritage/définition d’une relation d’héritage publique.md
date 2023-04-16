En programmation orientée objet, l'héritage est un mécanisme qui permet à une classe d'hériter des caractéristiques d'une autre classe. L'héritage public est l'une des trois formes d'héritage disponibles en C++, avec l'héritage privé et l'héritage protégé.

Dans une relation d'héritage public, la classe dérivée hérite des membres publics et protégés de la classe de base en conservant leur niveau d'accès. Cela signifie que les membres publics de la classe de base peuvent être accédés directement depuis la classe dérivée, tout comme si la classe dérivée les avait elle-même définis.

Voici un exemple pour illustrer cela :

```cpp
class Animal {
public:
    void respirer() {
        cout << "Je respire de l'oxygène." << endl;
    }
};

class Chien : public Animal {
public:
    void aboyer() {
        cout << "Wouaf wouaf !" << endl;
    }
};

int main() {
    Chien monChien;
    monChien.respirer(); // Héritage de la fonction respirer de la classe Animal
    monChien.aboyer(); // Appel de la fonction aboyer de la classe Chien
    return 0;
}
```

Dans cet exemple, la classe Chien hérite publiquement de la classe Animal. Le membre public respirer() de la classe Animal peut être appelé directement depuis la classe Chien, qui peut également définir ses propres membres publics et protégés.

L'héritage public permet donc de créer des classes spécialisées qui étendent les fonctionnalités des classes de base tout en préservant l'interface publique de la classe de base. Il permet également de réutiliser le code existant de manière efficace.