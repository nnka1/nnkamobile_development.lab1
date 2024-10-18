# Лабораторная работа №1. Создание Activity и передача параметров между ними.
Выполнила: Усова Валентина, ИСП-221С
## Что делает приложение?

Приложение демонстрирует простой пример передачи данных между двумя активити. 

## Работа приложения

### 1.  MainActivity
* Отображает кнопку btn1.
* При нажатии на кнопку: 
1. Создается Intent для запуска MainActivity2.
2. В Intent передается параметр "familyName" со значением "Усова". 
3. Вызывается метод startActivity() для запуска MainActivity2.
   ![image](https://github.com/user-attachments/assets/a81ef191-68ec-488a-953c-c8c54cdb55bf)
   


### 2.  MainActivity2

* Получает переданный параметр "familyName" из Intent.

  ![image](https://github.com/user-attachments/assets/19a9deef-a521-442e-af06-8632e28cf597)
