Les types-template, tout comme les fonctions-template, sont des modèles (templates) qui permettent de créer des types génériques. Ils permettent de définir des types de données qui peuvent être utilisés avec différents types d'arguments.

La syntaxe pour définir un type-template est la suivante :

```cpp
template <typename T>
struct nom_type {
  // membres et méthodes du type
};
```

ou bien :


```cpp
template <typename T>
class nom_type {
  // membres et méthodes du type
};
```

Dans cet exemple, T est un paramètre de type générique qui peut être remplacé par n'importe quel type de données. Les membres et méthodes du type sont définis à l'intérieur de la structure ou de la classe, comme pour n'importe quelle structure ou classe ordinaire.

Voici un exemple simple de type-template :

```cpp
template <typename T>
struct point {
  T x;
  T y;
};

point<int> p1 { 1, 2 };
point<double> p2 { 3.5, 4.2 };
```

Dans cet exemple, nous avons défini un type-template point qui contient deux membres de type T : x et y. Nous avons ensuite créé deux instances de ce type, l'une avec des valeurs entières et l'autre avec des valeurs à virgule flottante.

Les types-template peuvent également avoir plusieurs paramètres de type générique, ainsi que des paramètres avec des types spécifiques. Par exemple :

```cpp
template <typename T, int N>
class array {
  T data[N];
public:
  T& operator[](int i) { return data[i]; }
};

array<int, 5> a1 { 1, 2, 3, 4, 5 };
array<double, 3> a2 { 1.2, 2.3, 3.4 };
```

Dans cet exemple, nous avons défini un type-template array qui contient un tableau de taille N et de type T. Nous avons également défini une méthode d'indexation pour accéder aux éléments du tableau. Nous avons ensuite créé deux instances de ce type, l'une avec un tableau d'entiers de taille 5, et l'autre avec un tableau de valeurs à virgule flottante de taille 3.

Les types-template sont très utiles pour créer des structures de données génériques qui peuvent être utilisées avec différents types de données. Ils sont largement utilisés dans la bibliothèque standard de C++, ainsi que dans de nombreuses bibliothèques tierces.