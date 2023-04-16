La bibliothèque algorithm de C++ contient un ensemble de fonctions pour effectuer des opérations courantes sur des conteneurs. Voici quelques exemples d'utilisation de cette bibliothèque :

1.  Tri d'un vecteur

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> v = { 5, 2, 1, 4, 3 };
    std::sort(v.begin(), v.end());
    return 0;
}
```

2.  Recherche d'un élément dans un vecteur :

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> v = { 5, 2, 1, 4, 3 };
    int x = 4;
    auto it = std::find(v.begin(), v.end(), x);
    if (it != v.end()) {
        std::cout << "Element found at position " << std::distance(v.begin(), it) << "\n";
    } else {
        std::cout << "Element not found\n";
    }
    return 0;
}
```

3.  Copie des éléments d'un vecteur dans un autre vecteur :

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> v1 = { 5, 2, 1, 4, 3 };
    std::vector<int> v2(v1.size());
    std::copy(v1.begin(), v1.end(), v2.begin());
    return 0;
}
```

4.  Transformation des éléments d'un vecteur en appliquant une fonction :

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> v = { 5, 2, 1, 4, 3 };
    std::transform(v.begin(), v.end(), v.begin(), [](int x) { return x * 2; });
    return 0;
}
```

La bibliothèque algorithm offre de nombreuses autres fonctions pour effectuer des opérations sur les conteneurs, comme la suppression d'éléments, la fusion de conteneurs, la comparaison de conteneurs, etc. Il est important de consulter la documentation pour en savoir plus sur toutes les fonctionnalités disponibles.


Voici quelques autres fonctions utiles de la bibliothèque algorithmes :

- std::reverse: permet de renverser l'ordre des éléments d'une séquence.

-std::unique: permet de supprimer les éléments consécutifs en doublon dans une séquence.

- std::merge: permet de fusionner deux séquences triées en une seule séquence triée.

- std::partition: permet de partitionner une séquence en deux parties en fonction d'un prédicat donné.

- std::rotate: permet de faire pivoter les éléments d'une séquence vers la gauche ou vers la droite.

- std::count_if: permet de compter le nombre d'éléments dans une séquence qui vérifient un certain prédicat.

- std::min_element et std::max_element: permettent de trouver le plus petit ou le plus grand élément d'une séquence.

- std::sort: permet de trier une séquence.


