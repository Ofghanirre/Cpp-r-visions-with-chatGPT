L'utilisation du mot-clé const en C++ permet de déclarer une variable, une fonction ou une méthode comme étant constante, c'est-à-dire qu'elle ne peut pas être modifiée.

Pour les variables, cela signifie que leur valeur ne peut pas être modifiée après leur initialisation. Par exemple :

```cpp
const int n = 10; // n est une constante qui ne peut pas être modifiée
```

Pour les fonctions et les méthodes, cela signifie qu'elles ne modifient pas l'état de l'objet sur lequel elles sont appelées. Par exemple :

```cpp
class Exemple {
public:
    int getValeur() const {
        return valeur_;
    }
private:
    int valeur_;
};
```

Dans cet exemple, la méthode getValeur() est déclarée comme étant const, ce qui signifie qu'elle ne modifie pas l'état de l'objet Exemple sur lequel elle est appelée.

L'utilisation de const permet de rendre le code plus sûr et plus lisible, en évitant les erreurs de modification de valeurs qui ne devraient pas l'être.