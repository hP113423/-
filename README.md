#include <iostream>
#include <cmath>
#include <iomanip>

int main() {
    double x1, x2, h, x, f;

    // Введення даних
    std::cout << "Введіть значення x1, x2, h: ";
    std::cin >> x1 >> x2 >> h;

    // Перевірка правильності введення даних
    while (x1 > x2 || h <= 0) {
        std::cout << "Неправильно введені дані. Будь ласка, введіть їх знову: ";
        std::cin >> x1 >> x2 >> h;
    }

    std::cout << std::setw(10) << "x" << std::setw(10) << "f(x)" << std::endl;

    for (x = x1; x <= x2; x += h) {
        // Обчислення значення функції
        if (x == 3) {
            std::cout << std::setw(10) << x << std::setw(10) << "не визн" << std::endl;
        } else {
            f = std::log(x + 2) / (x - 3);
            if (std::abs(f) > 1e9) {
                std::cout << std::setw(10) << x << std::setw(10) << "переповн" << std::endl;
            } else {
                std::cout << std::setw(10) << x << std::setw(10) << f << std::endl;
            }
        }
    }

    return 0;
}
