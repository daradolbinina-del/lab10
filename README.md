# Домашнее задание к работе 10
## Условие задачи

Составьте программу, которая для заданной пользователем фигуры, например прямоугольника (треугольника или другой фигуры см. инидивидуальное задание работы 9) предлагает меню выбора одной из операций:
1) рассчитать площадь;
2) вывести определение фигуры;
3) нарисовать фигуру.

## 1. Алгоритм и блок-схема
## Алгоритм
1. Начало программы
2. Ввод данных пользователем:
   - `h` — высота 
3. Показать меню действий:
   1. Рассчитать площадь — вызвать функцию S(r, a)
   2. Вывести определение фигуры
   3. Нарисовать треугольник — вызвать draw_deltoid(r)
   4. Выйти из программы
4. Спросить, хочет ли пользователь продолжить
5. Если нет — завершить программу
6. Конец программы
   
### Блок-схема
<img width="1195" height="2500" alt="image" src="https://github.com/user-attachments/assets/b3d52815-79f7-40ce-8897-f6c897837d5c" />



## 2. Реализация программы

```
#define _CRT_SECURE_NO_WARNINGS
#define _USE_MATH_DEFINES
#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <math.h>



float S_triangle(float b, float h) {
    return (b * h) / 2;
}


void draw_triangle_outline(int h, char symbol) {
    for (int i = 1; i <= h; i++) {
        
        for (int j = 1; j <= h - i; j++)
            printf(" ");

        
        for (int j = 1; j <= 2 * i - 1; j++) {
            printf("%c", symbol);
        }
        printf("\n");
    }
}

int main() {
    setlocale(LC_ALL, "RUS");

    int choice;
    int h;
    float b;
    char symbol;

    while (1) {
        printf("\nВведите высоту остроугольного треугольника: ");
        scanf("%d", &h);

        printf("\n=== МЕНЮ ===\n");
        printf("1. Рассчитать площадь\n");
        printf("2. Вывести определение фигуры\n");
        printf("3. Нарисовать фигуру\n");
        printf("Выберите пункт меню: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            printf("Введите основание треугольника: ");
            scanf("%f", &b);
            printf("Площадь остроугольного треугольника: S = %.2f\n", S_triangle(b, h));
            break;

        case 2:
            printf("Остроугольный треугольник — треугольник, у которого все три угла острые (меньше 90°).\n");
            break;

        case 3:
            printf("Введите символ для рисования: ");
            scanf(" %c", &symbol);
            printf("\nОстроугольный треугольник:\n\n");
            draw_triangle_outline(h, symbol);
            break;

        default:
            printf("Неверный выбор. Попробуйте снова.\n");
        }

        printf("\nПродолжить? (y/n): ");
        char cont;
        scanf(" %c", &cont);
        if (cont == 'n' || cont == 'N') break;
    }

    return 0;
}

```


## 3. Результаты работы программы
<img width="1474" height="934" alt="image" src="https://github.com/user-attachments/assets/308d1309-89d6-46ad-89ea-37cf1cc5259d" />
