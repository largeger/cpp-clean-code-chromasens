# Übung – SOLID Prinzipien anwenden

## Ziel
In dieser Übung soll ein Verstoß gegen das **Open/Closed-Prinzip (OCP)** behoben werden.

## Aufgabe
Der folgende Code verstößt gegen das OCP, weil jede neue Zahlungsart den bestehenden Code verändert.

1. Identifiziere, warum das OCP verletzt ist.
2. Refaktoriere den Code so, dass neue Zahlungsarten hinzugefügt werden können, **ohne** die bestehende Logik zu ändern.

```cpp
#include <iostream>
#include <string>

class PaymentProcessor {
public:
    void process(const std::string& type) {
        if (type == "creditcard") {
            std::cout << "Processing credit card payment" << std::endl;
        } else if (type == "paypal") {
            std::cout << "Processing PayPal payment" << std::endl;
        } else if (type == "bank") {
            std::cout << "Processing bank transfer" << std::endl;
        }
    }
};

int main() {
    PaymentProcessor p;
    p.process("paypal");
}
```

---

### Hinweise
- Überlege, wie du das Verhalten über **Polymorphie** oder **Interfaces** erweiterbar machen kannst.
- Ziel: Der PaymentProcessor soll offen für Erweiterungen, aber geschlossen für Modifikationen sein.
