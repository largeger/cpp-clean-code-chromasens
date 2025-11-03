# Übung – Code Smells erkennen

## Ziel
In dieser Übung sollen typische **Code Smells** erkannt und beschrieben werden.

## Aufgabe
Analysiere den folgenden C++-Code.  
Er enthält mehrere Code Smells (z. B. zu lange Methode, duplizierte Logik, Magic Numbers).

1. Beschreibe, welche Smells du findest.
2. Schlage Verbesserungen vor.
3. Refaktoriere den Code so, dass er sauberer und wartbarer wird.

```cpp
#include <iostream>
#include <string>

void processOrder(std::string type, int quantity) {
    if (type == "A") {
        double price = 10.0 * quantity;
        if (quantity > 100) price *= 0.9;
        std::cout << "Order type A, total: " << price << std::endl;
    } else if (type == "B") {
        double price = 20.0 * quantity;
        if (quantity > 100) price *= 0.9;
        std::cout << "Order type B, total: " << price << std::endl;
    } else if (type == "C") {
        double price = 30.0 * quantity;
        if (quantity > 100) price *= 0.9;
        std::cout << "Order type C, total: " << price << std::endl;
    }
}

int main() {
    processOrder("A", 120);
}
```

---

### Hinweise
- Überlege, wie du Struktur, Lesbarkeit und Erweiterbarkeit verbessern kannst.
