En C++, un constructeur est une méthode spéciale d'une classe qui est appelée lorsqu'un objet est créé. Le constructeur est utilisé pour initialiser les attributs de la classe et peut être surchargé pour accepter différents types d'arguments.

La syntaxe pour définir un constructeur est la suivante :

```cpp
class nom_classe {
public:
  nom_classe(); // constructeur par défaut
  nom_classe(int arg1, double arg2); // constructeur surchargé
};
```

Le constructeur par défaut est appelé lorsque l'objet est créé sans argument :

```cpp
nom_classe obj; // appel du constructeur par défaut
```

Le constructeur surchargé est appelé lorsque l'objet est créé avec des arguments :

```cpp
nom_classe obj(42, 3.14); // appel du constructeur surchargé
```

La liste d'initialisation est une syntaxe spéciale pour initialiser les attributs de la classe dans le constructeur. Elle est utilisée pour éviter la duplication de code dans le constructeur et pour garantir que les attributs sont initialisés avant que le corps du constructeur ne commence à s'exécuter.

La syntaxe pour la liste d'initialisation est la suivante :

```cpp
class nom_classe {
public:
  nom_classe(int arg1, double arg2) : attribut1(arg1), attribut2(arg2) {
    // corps du constructeur
  }
private:
  int attribut1;
  double attribut2;
};
```

Dans cet exemple, les attributs de la classe nom_classe sont initialisés à l'aide de la liste d'initialisation dans le constructeur surchargé. La liste d'initialisation est placée entre deux points-virgules, suivis du corps du constructeur entre accolades.

La liste d'initialisation peut être utilisée pour initialiser les attributs de la classe à l'aide de valeurs littérales, de variables locales, d'expressions, d'autres attributs de la classe, ou même d'appels de fonctions :

```cpp
class nom_classe {
public:
  nom_classe(int arg1, double arg2) : 
    attribut1(arg1), 
    attribut2(arg2 + 1.0), 
    attribut3("valeur par défaut"),
    attribut4(fonction(arg1, arg2))
  {
    // corps du constructeur
  }
private:
  int attribut1;
  double attribut2;
  std::string attribut3;
  bool attribut4;
};
```

Dans cet exemple, les attributs attribut1 et attribut2 sont initialisés à l'aide des arguments du constructeur, attribut3 est initialisé à l'aide d'une chaîne de caractères littérale, et attribut4 est initialisé à l'aide d'un appel de fonction.