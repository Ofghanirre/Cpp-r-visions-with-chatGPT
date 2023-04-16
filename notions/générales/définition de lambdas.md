Les lambdas sont des fonctions anonymes qui peuvent être définies de manière inline, directement dans le code. Elles peuvent être considérées comme des raccourcis pour la définition de fonctions simples et courtes.

La syntaxe d'une lambda est la suivante :

```cpp
[capture_list] (param_list) -> return_type { body }
```

- capture_list : liste optionnelle de variables capturées depuis le contexte dans lequel la lambda est définie. Cette liste est encadrée par des crochets []. Les variables capturées sont utilisées dans la définition de la lambda mais ne sont pas des paramètres de la fonction. 

#### Les variables sont captées à la création de la lambda et sont par défaut en const, on peut donc imaginée qu'elles sont déclarées en inline const, et que pour les rendre modifiables il faut passer par une référence. (voir revision.html)

- param_list : liste des paramètres formels de la lambda, séparés par des virgules et encadrés par des parenthèses.
- return_type : type de retour de la lambda, optionnel si le type peut être déduit automatiquement.
- body : le corps de la lambda, qui peut contenir une ou plusieurs instructions.

Voici un exemple de définition d'une lambda qui calcule la somme de deux entiers :

```cpp
auto sum = [](int a, int b) -> int { return a + b; };
```

Dans cet exemple, nous définissons une lambda qui prend deux entiers en paramètres et retourne leur somme. Nous utilisons le mot-clé auto pour que le compilateur détermine automatiquement le type de la lambda. La capture list est vide car nous n'avons pas besoin de variables du contexte extérieur.

Les lambdas peuvent également être utilisées avec des algorithmes de la bibliothèque standard de C++, comme std::for_each, std::transform, std::sort, etc. Par exemple :

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> v = { 1, 2, 3, 4, 5 };
    std::for_each(v.begin(), v.end(), [](int n){ std::cout << n << " "; });
    std::cout << std::endl;
    return 0;
}
```

Dans cet exemple, nous utilisons std::for_each pour parcourir un vecteur d'entiers et afficher chaque élément à l'écran en utilisant une lambda qui prend un entier en paramètre et ne retourne rien.

