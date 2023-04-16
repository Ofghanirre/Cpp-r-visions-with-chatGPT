En C++, la classe std::string est utilisée pour manipuler des chaînes de caractères. Elle est définie dans la bibliothèque standard string et offre de nombreuses fonctionnalités pour travailler avec des chaînes de caractères.

Voici quelques exemples d'utilisation de std::string :

1.  Création d'une chaîne de caractères vide :

```cpp
std::string s;
```

2.  Création d'une chaîne de caractères initialisée avec une valeur :

```cpp
std::string s = "Hello, world!";
```

3.  Ajout d'un caractère à la fin de la chaîne de caractères :

```cpp
s.push_back('!');
```

4.  Concaténation de deux chaînes de caractères :

```cpp
std::string s1 = "Hello, ";
std::string s2 = "world!";
std::string s3 = s1 + s2;
```

5.  Accès aux caractères individuels de la chaîne de caractères :

```cpp
char c = s[0];
```

6.  Calcul de la longueur de la chaîne de caractères :

```cpp
int len = s.length();
```

7.  Recherche de sous-chaînes dans la chaîne de caractères :

```cpp
std::string s = "Hello, world!";
size_t pos = s.find("world");
if (pos != std::string::npos) {
    std::cout << "Substring found at position " << pos << std::endl;
} else {
    std::cout << "Substring not found" << std::endl;
}
```

Conversion de la chaîne de caractères en nombre entier :

```cpp
std::string s = "42";
int n = std::stoi(s);
``` 

Il est important de noter que std::string gère automatiquement la gestion de la mémoire, donc il n'est pas nécessaire de s'en occuper manuellement comme avec les chaînes de caractères de style C.