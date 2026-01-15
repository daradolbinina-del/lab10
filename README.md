# Домашнее задание к работе 10
## Условие задачи
Напишите программу, которая вычисляет размер типа данных short int в байтах. 

## 1. Алгоритм и блок-схема
## Алгоритм
1. Начало.
2. Инициализируем массив short_arr[2];
3. printf("размер типа данных short int в байтах: %ld\n", (char*)(&short_arr[1]) - (char*)(&short_arr[0]));
4. Возвращаем 0;
5. Конец.
### Блок-схема
<img width="411" height="529" alt="image" src="https://github.com/user-attachments/assets/b6946267-f314-4582-81f8-b431309ee117" />




## 2. Реализация программы

```
#define _CRT_SECURE_NO_DEPRECATE
#include <stdio.h>
#include <locale.h>

void main()
{
	setlocale(LC_ALL, "RUS");
	short int short_arr[2];
	printf("размер типа данных short int в байтах: %ld\n", (char*)(&short_arr[1]) - (char*)(&short_arr[0]));
	return 0;
}

```


## 3. Результаты работы программы
<img width="547" height="72" alt="image" src="https://github.com/user-attachments/assets/e5cadee9-8029-4f2f-b4aa-5bee2c6b69f5" />

