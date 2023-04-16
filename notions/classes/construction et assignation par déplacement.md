La construction et l'assignation par déplacement sont des fonctionnalités introduites en C++11 qui permettent de transférer les ressources d'un objet à un autre objet, plutôt que de les copier.

La construction par déplacement est appelée lorsqu'un objet est initialisé à l'aide d'un autre objet, mais plutôt que de copier l'objet, ses ressources sont transférées à l'objet en cours de construction. La construction par déplacement peut être définie en créant un constructeur de déplacement dans la classe. Le constructeur de déplacement utilise la syntaxe MyClass(MyClass&& other) où other est une référence rvalue de type MyClass. L'opérateur && signifie que other est un objet temporaire, c'est-à-dire un objet qui n'a pas de nom ou qui va bientôt être détruit, et qu'il peut être déplacé de manière efficace.

```cpp
class MyClass {
public:
  // Constructeur de déplacement
  MyClass(MyClass&& other) noexcept {
    // Transfert de ressources de other à this
  }
};
```

L'assignation par déplacement est similaire à la construction par déplacement, mais plutôt que de créer un nouvel objet, les ressources d'un objet existant sont transférées à un autre objet existant. L'assignation par déplacement peut être définie en créant un opérateur d'assignation de déplacement dans la classe. L'opérateur d'assignation de déplacement utilise la syntaxe MyClass& operator=(MyClass&& other) où other est une référence rvalue de type MyClass.

```cpp
class MyClass {
public:
  // Opérateur d'assignation de déplacement
  MyClass& operator=(MyClass&& other) noexcept {
    // Transfert de ressources de other à this
    return *this;
  }
};
```

Il est important de noter que les opérateurs de déplacement sont déclarés avec le mot-clé noexcept. Cela indique que l'opération de déplacement ne peut pas échouer en raison d'une exception, ce qui permet au compilateur d'optimiser le code pour une meilleure performance.

La construction et l'assignation par déplacement sont particulièrement utiles pour les objets qui contiennent des ressources coûteuses, comme des tableaux dynamiques, des objets de grande taille ou des ressources système. En utilisant la construction et l'assignation par déplacement, vous pouvez éviter de copier ces ressources, ce qui peut améliorer considérablement les performances de votre programme.