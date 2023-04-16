Les exceptions standards sont des exceptions prédéfinies dans la bibliothèque standard de C++. La bibliothèque fournit plusieurs classes d'exception standard qui héritent de la classe std::exception, située dans l'en-tête <stdexcept>.

Voici quelques-unes des classes d'exceptions standards les plus courantes :

- std::logic_error : représente une erreur liée à la logique du programme, comme une violation de la précondition d'une fonction.

- std::runtime_error : représente une erreur liée à l'exécution du programme, comme une erreur de fichier manquant.

- std::invalid_argument : est une sous-classe de std::logic_error et représente une erreur causée par des arguments passés à une fonction qui ne sont pas valides.

- std::out_of_range : est une sous-classe de std::logic_error et représente une erreur qui se produit lorsqu'un index est hors limites.

Voici un exemple d'utilisation de std::runtime_error pour signaler une erreur :


```cpp
#include <stdexcept>

void myFunction()
{
    if (/* condition d'erreur */) {
        throw std::runtime_error("Erreur lors de l'exécution de myFunction()");
    }
}
```

Cet exemple utilise la fonction throw pour lancer une exception de type std::runtime_error avec le message "Erreur lors de l'exécution de myFunction()". Cette exception peut être attrapée et gérée dans un bloc try-catch approprié.

Il est recommandé de dériver vos propres classes d'exceptions à partir des classes d'exceptions standard appropriées.