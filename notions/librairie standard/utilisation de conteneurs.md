En C++, les conteneurs sont des classes qui permettent de stocker et de gérer des ensembles d'objets d'un certain type. Les conteneurs les plus couramment utilisés sont :

- Les tableaux dynamiques (vecteurs) : stockent des éléments dans un tableau dynamique redimensionnable.
- Les listes : stockent des éléments dans une liste doublement chaînée.
- Les piles et les files : stockent des éléments selon un principe de dernière entrée, première sortie (piles) ou premier entré, premier sorti (files).
- Les ensembles : stockent des éléments uniques dans un ordre trié.
- Les dictionnaires (map) : stockent des associations clé-valeur.

Voici un exemple d'utilisation d'un vecteur pour stocker des entiers :

```cpp
#include <vector>
#include <iostream>

int main() {
  std::vector<int> v; // Création du vecteur

  // Ajout d'éléments dans le vecteur
  v.push_back(1);
  v.push_back(2);
  v.push_back(3);

  // Parcours des éléments du vecteur avec une boucle for
  for (int i = 0; i < v.size(); i++) {
    std::cout << v[i] << " ";
  }

  // Parcours des éléments du vecteur avec un itérateur
  for (std::vector<int>::iterator it = v.begin(); it != v.end(); it++) {
    std::cout << *it << " ";
  }

  return 0;
}
```

On peut également utiliser des algorithmes de la bibliothèque standard pour effectuer des opérations sur les conteneurs, comme trier un vecteur ou chercher un élément dans une liste :

```cpp
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
  std::vector<int> v = {3, 1, 4, 1, 5, 9, 2, 6, 5, 3};

  // Tri du vecteur
  std::sort(v.begin(), v.end());

  // Affichage des éléments triés
  for (int i : v) {
    std::cout << i << " ";
  }

  // Recherche de l'élément 5 dans le vecteur
  auto it = std::find(v.begin(), v.end(), 5);
  if (it != v.end()) {
    std::cout << "L'élément 5 se trouve à l'indice " << std::distance(v.begin(), it) << std::endl;
  } else {
    std::cout << "L'élément 5 n'a pas été trouvé" << std::endl;
  }

  return 0;
}
```