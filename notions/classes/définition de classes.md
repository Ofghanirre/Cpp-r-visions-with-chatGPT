En C++, une classe est une structure de données qui permet de regrouper des données et des fonctions qui opèrent sur ces données. Une classe peut être considérée comme un type de données personnalisé, avec ses propres propriétés et méthodes.

La syntaxe pour définir une classe est la suivante :

```cpp
class nom_classe {
  // membres et méthodes de la classe
};
```

Les membres de la classe peuvent être des variables de données (appelées "attributs" ou "propriétés"), ainsi que des fonctions (appelées "méthodes"). Les membres de la classe peuvent être publics, privés ou protégés. Les membres publics peuvent être utilisés à l'extérieur de la classe, tandis que les membres privés et protégés ne sont accessibles qu'à l'intérieur de la classe.

Voici un exemple simple de classe :

```cpp
class point {
public:
  int x;
  int y;
  
  void afficher() {
    std::cout << "x = " << x << ", y = " << y << std::endl;
  }
};

point p1 { 1, 2 };
p1.afficher();
```

Dans cet exemple, nous avons défini une classe point qui contient deux attributs x et y, ainsi qu'une méthode afficher() qui affiche les coordonnées du point. Nous avons ensuite créé une instance de cette classe et appelé sa méthode afficher().

Les classes peuvent également être utilisées pour créer des objets qui ont leur propre état et leur propre comportement. Les objets sont des instances de la classe, créées à l'aide du mot-clé new :

```cpp
point* p2 = new point { 3, 4 };
p2->afficher();
```

Dans cet exemple, nous avons créé un point p2 à l'aide de l'opérateur new, puis appelé sa méthode afficher() à l'aide de l'opérateur ->.

Les classes sont largement utilisées en C++ pour encapsuler des données et des fonctions liées à ces données, afin de faciliter la programmation orientée objet. Les classes sont également utilisées dans de nombreuses bibliothèques standard de C++, ainsi que dans de nombreuses bibliothèques tierces.