# Übung – Lange Methode refaktorisieren

## Ziel
Eine lange, schwer verständliche Methode soll in kleinere, klar benannte Methoden zerlegt werden.

## Aufgabe
Der folgende Code enthält mehrere Verantwortlichkeiten in einer Funktion.

1. Identifiziere die logischen Abschnitte.
2. Extrahiere sie in eigene Methoden mit sinnvollen Namen.
3. Ziel: kürzere, besser lesbare und testbare Methoden.

```cpp
#include <iostream>
#include <string>

class SalesReport {
public:
    void generate(const std::string& name, int sales, int refunds) {
        std::cout << "Generating report..." << std::endl;
        int netSales = sales - refunds;
        double commission = netSales * 0.1;
        std::cout << "Name: " << name << std::endl;
        std::cout << "Sales: " << sales << ", Refunds: " << refunds << std::endl;
        std::cout << "Net: " << netSales << ", Commission: " << commission << std::endl;
        if (netSales > 1000)
            std::cout << "Excellent performance!" << std::endl;
        else
            std::cout << "Needs improvement." << std::endl;
    }
};

int main() {
    SalesReport().generate("Alice", 1500, 200);
}

```

---

### Hinweise
- Denke an **Single Responsibility** pro Methode.
- Überlege, wie du Berechnung und Darstellung trennen kannst.
