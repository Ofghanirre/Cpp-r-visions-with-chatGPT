Lorsque vous exécutez un programme C++, vous pouvez passer des arguments en ligne de commande. Ces arguments sont traités par le programme à l'aide des paramètres de la fonction main().

La signature de la fonction main() est la suivante :

```cpp
int main(int argc, char *argv[])
```
où argc est le nombre d'arguments passés à la ligne de commande et argv est un tableau de chaînes de caractères qui contient ces arguments.

Voici un exemple simple pour afficher tous les arguments passés en ligne de commande :


```cpp
#include <iostream>

int main(int argc, char *argv[])
{
    std::cout << "Nombre d'arguments : " << argc << std::endl;

    for (int i = 0; i < argc; i++)
    {
        std::cout << "Argument " << i << " : " << argv[i] << std::endl;
    }

    return 0;
}
```
Dans cet exemple, nous avons utilisé une boucle for pour parcourir tous les arguments passés en ligne de commande et les afficher à l'écran.

Supposons que vous ayez compilé ce programme sous le nom "programme.exe". Vous pouvez maintenant exécuter ce programme avec des arguments en ligne de commande comme ceci :

```
programme.exe arg1 arg2 arg3
```

Le programme affichera alors :
```yaml
Nombre d'arguments : 4
Argument 0 : programme.exe
Argument 1 : arg1
Argument 2 : arg2
Argument 3 : arg3
```
Notez que le premier argument (argv[0]) est toujours le nom du programme lui-même.