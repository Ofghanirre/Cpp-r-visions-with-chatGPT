# Fiche Révision C++

## Exercice 1 - Algorithmes & lambdas

### 1

[Documentation Algorithm](https://en.cppreference.com/w/cpp/algorithm)

| Demande  | fonctions          | exemple |
| :--- |:-:| :---------------: |
| Je souhaite récupérer le premier élément d’une plage de chaînes qui contient exactement 8 lettres. | `find_if` | `find_if(first, last, [](auto elem){ return elem.size() == 8; })` |
| Je souhaite calculer la multiplication terme à terme entre deux plages contenant le même nombre de valeurs. | `transform` | `transform(first1, last1, first2, firstDest, [](T a, T b){ return a * b; })` |
| Je souhaite assigner la valeur 3 à chacun des éléments d’une plage. | `fill` | `fill(first1, last1, 3)` |
| Je souhaite savoir si tous les éléments d’une plages sont négatifs. | `all_of` | `all_of(first1, last1, [](int value){ return value < 0;})` |
| Je souhaite réordonner une plage du plus grand élément au plus petit. | `sort` | `sort(first1, last1, [](T a, T b) { return a <= b})` |
| Je souhaite calculer le nombre total de caractères présents dans une plage qui contient des mots | `reduce` | `reduce(first1, last1, T init, [](T value){ return value.size();})` |

### 2 

```cpp
const auto values = std::vector { 0, 15, -3, 6, -2, 18, 27 }; // -> valeur
auto bounds = std::pair { 3, 10 }; // -> valeur

const auto predicate = [bounds]  /* -> capture d'une valeur => copie */
/* Pour faire une ref: [&bounds] -> là on passe par ref donc ça updatera */
                        (int p) { return bounds.first <= p && p <= bounds.second; };

bounds = { 10, 20 };

std::cout << std::count_if(values.begin(), values.end(), predicate) << std::endl; // -> 6
```

```cpp
const auto values = std::vector { 0, 15, -3, 6, -2, 18, 27 };
auto bounds = std::pair { 3, 10 };

const auto predicate = [min = bounds.first, 
                        max = &bounds.second] /* ERROR -> on peut pas passer par ref et stocker dans une capture par valeur*/
/* Pour faire une ref:  &max = bounds.second] -> là max est une ref vers bounds.second et s'actualisera donc */
                        (int p) { return min <= p && p <= max; };

bounds = { 10, 20 };

std::cout << std::count_if(values.begin(), values.end(), predicate) << std::endl; // -> 6, 15, 18
```

```cpp
const auto values = std::vector { 0, 15, -3, 6, -2, 18, 27 };
auto sum_odd = 0;

std::for_each(values.begin(), values.end(), 
    [&sum_odd, 
    odd = false]
    (int v)
/*  mutable -> toutes les captures par valeur sont désormais mutables */  
{
	sum_odd += odd ? v : 0;
	odd = !odd; /* ERROR -> de base les captures sont inline const équivalents, donc immutable */
});

std::cout << sum_odd << std::endl;
```

### 3
[https://godbolt.org/z/6nKq4G7Ma](https://godbolt.org/z/6nKq4G7Ma)
```cpp
#include <algorithm>
#include <iostream>
#include <vector>

#define ANSWER [](auto& v) { v *= 2; }                     // <-- modifiez ici

int main()
{
    auto values = std::vector { 20, 0, -2, 15 };
    std::for_each(values.begin(), values.end(), ANSWER);

    // Resultat attendu : 40 0 -4 30
    for (const auto& v: values)
    {
        std::cout << v << " ";
    }
}
```

[https://godbolt.org/z/jz1EYq4WM](https://godbolt.org/z/jz1EYq4WM)
```cpp
#define ANSWER_1 std::find_if   // to find element in list
#define ANSWER_2 [&searched](std::string value) { return value == searched; } // find_if predicate matches the searched value, reference to avoid copy
#define ANSWER_3 std::distance // calculate the distance between 2 iterator values, here to know which position on the vector.

int main()
{
    auto searched = std::string { "" };
    std::cin >> searched;

    const auto values = std::list<std::string> { "Laura", "Etienne", "Antoine", "Emilie" };
    const auto it = ANSWER_1(values.begin(), values.end(), ANSWER_2);

    // Resultat attendu :
    // - si searched == "Hugo" : not found
    // - si searched == "Etienne" : 1
    // - si searched == "Emilie" : 3
    if (it == values.end())
    {
        std::cout << "not found" << std::endl;
    }
    else
    {
        std::cout << ANSWER_3(values.begin(), it) << std::endl;
    }
}
```

### 4

[https://godbolt.org/z/q1vnYsWz6](https://godbolt.org/z/q1vnYsWz6)

```cpp
#include <algorithm>
#include <cmath>
#include <iostream>
#include <map>
#include <sstream>
#include <regex>
#include <functional>

class Calculator
{
public:
    /*fcns*/
    void register_unary(std::string id, std::function<float(float)> unary_function) {
        _unary_fcn[id] = unary_function;
    }

    void register_binary(std::string id, std::function<float(float, float)> binary_function) {
        _binary_fcn[id] = binary_function;
    }

    float operator()(std::string fcn, float n1, float n2) {
        return _binary_fcn[fcn](n1, n2);
    }

    float operator()(std::string fcn, float n1) {
        return _unary_fcn[fcn](n1);
    }
private:
    std::map<std::string, std::function<float(float)>> _unary_fcn;          // declare a function that take a float and returns a new one
    std::map<std::string, std::function<float(float, float)>> _binary_fcn;  // declare a function that take 2 floats and returns a new one
};

bool parse_binary_op(const std::string& line, std::string& id, float& n1, float& n2)
{
    const auto regex = std::regex { "\\s*(\\d+(\\.\\d+)?)\\s*([^0-9]+?)\\s*(\\d+(\\.\\d+)?)\\s*" };
    
    auto match = std::smatch {};
    if (!std::regex_match(line, match, regex))
    {
        return false;
    }

    n1 = std::stof(match.str(1));
    n2 = std::stof(match.str(4));
    id = match.str(3);

    return true;
}

bool parse_unary_op(const std::string& line, std::string& id, float& n1)
{
    const auto regex = std::regex { "\\s*([^0-9]+?)\\s*(\\d+(\\.\\d+)?)" };
    
    auto match = std::smatch {};
    if (!std::regex_match(line, match, regex))
    {
        return false;
    }

    id = match.str(1);
    n1 = std::stof(match.str(2));

    return true;
}


int main()
{
    auto calculator = Calculator {};

    calculator.register_unary("square", [](float n) { return n * n; });
    calculator.register_unary("-", [](float n) { return -n; });
    calculator.register_unary("sin", sinf);
    calculator.register_unary("cos", cosf);
    calculator.register_binary("+", [](float a, float b) { return a + b; });
    calculator.register_binary("-", [](float a, float b) { return a - b; });

    while (true)
    {
        auto line = std::string {};
        if (std::getline(std::cin, line).fail())
        {
            break;
        }

        auto fcn = std::string {};
        auto n1 = 0.f;
        auto n2 = 0.f;

        if (parse_binary_op(line, fcn, n1, n2))
        {
            std::cout << fcn << "( " << n1 << " , " << n2 << " ) = ";
            std::cout << calculator(fcn, n1, n2) << std::endl; 
        }
        else if (parse_unary_op(line, fcn, n1))
        {
            std::cout << fcn << "( " << n1 << " ) = ";
            std::cout << calculator(fcn, n1) << std::endl; 
        }
    }
}