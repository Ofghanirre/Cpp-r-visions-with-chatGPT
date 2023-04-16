Les fonctions-template sont des fonctions qui peuvent être utilisées avec différents types de données. Elles sont définies à l'aide d'un modèle (template) qui décrit le comportement de la fonction pour tous les types de données possibles.

La syntaxe pour définir une fonction-template est la suivante :

```cpp
template <typename T>
ret_type nom_fonction(paramètres) {
  // corps de la fonction
}
```

où T est un paramètre de type générique qui peut être remplacé par n'importe quel type de données, et ret_type est le type de données que la fonction retourne. Les paramètres et le corps de la fonction sont similaires à ceux d'une fonction ordinaire.

Voici un exemple simple de fonction-template qui calcule la somme de deux valeurs :

```cpp
template <typename T>
T sum(T a, T b) {
  return a + b;
}
```

Dans cet exemple, T est le paramètre de type générique qui peut être remplacé par n'importe quel type de données, et la fonction retourne une valeur de ce même type. Le corps de la fonction consiste simplement en l'addition des deux paramètres.

Pour utiliser cette fonction-template, il suffit de spécifier le type de données que l'on souhaite utiliser en remplaçant T par ce type :

```cpp
int a = 5, b = 7;
double c = 2.5, d = 1.2;

std::cout << sum<int>(a, b) << std::endl;    // affiche 12
std::cout << sum<double>(c, d) << std::endl; // affiche 3.7
```

Dans cet exemple, nous appelons la fonction-template sum avec différents types de données en spécifiant le type entre les chevrons <>.

Les fonctions-template peuvent également avoir plusieurs paramètres de type génériques, ainsi que des paramètres avec des types spécifiques. Par exemple :

```cpp
template <typename T, typename U>
T multiply(T a, U b) {
  return a * b;
}
```

Dans cette fonction-template, nous avons deux paramètres de type générique T et U, et la fonction retourne une valeur de type T. Le corps de la fonction consiste simplement en la multiplication des deux paramètres.

Les fonctions-template sont très utiles pour écrire du code générique qui peut être utilisé avec différents types de données. Elles sont largement utilisées dans la bibliothèque standard de C++, ainsi que dans de nombreuses bibliothèques tierces.