# Лабораторная работа №1. Создание Activity и передача параметров между ними.
Выполнила: Усова Валентина, ИСП-221С
## Что делает приложение?

Приложение демонстрирует простой пример передачи данных между двумя активити. 

## Работа приложения

### 1.  MainActivity
1.1 Отображает кнопку btn1.

1.2. При нажатии на кнопку:
* Создается Intent для запуска MainActivity2.
* В Intent передается параметр "familyName" со значением "Усова". 
* Вызывается метод startActivity() для запуска MainActivity2.
   ![image](https://github.com/user-attachments/assets/a81ef191-68ec-488a-953c-c8c54cdb55bf)
   


### 2.  MainActivity2

2.1. Получает переданный параметр "familyName" из Intent.

2.2 Отображает значение параметра в текстовом поле.

  ![image](https://github.com/user-attachments/assets/19a9deef-a521-442e-af06-8632e28cf597)
  
## Как собрать проект?
1. Загрузка или клонирование репозитория:
* Скачайте файлы проекта (ZIP-архив) и разархивируйте их в удобную папку или клонируйте репозиторий с помощью команды git clone [URL репозитория].

2. Открытие проекта в Android Studio:
* Откройте Android Studio.
* В главном окне выберите "Open an existing Android Studio project".
* Найдите папку, в которую вы скачали или клонировали проект, и выберите файл build.gradle.

3. Запуск приложения:
* В Android Studio, нажмите кнопку "Run" (зеленый треугольник) на панели инструментов.
* Выберите эмулятор или подключенное Android-устройство, на котором вы хотите запустить приложение.
* Дождитесь завершения сборки и запуска приложения.

## Исходный код:
### MainActivity
```jsva
package com.example.myapplication

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat
import android.widget.Button
import android.content.Intent


class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        enableEdgeToEdge()

        val button = findViewById<Button>(R.id.btn1)

        button.setOnClickListener {
            val intent = Intent(this, MainActivity2::class.java)
            intent.putExtra("familyName", "Усова")

            startActivity(intent)
        }

    }
}
```
### MainActivity2
```jsva
package com.example.myapplication

import android.os.Bundle
import android.widget.TextView
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity2 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main2)

        val familyName = intent.getStringExtra("familyName")

        val textView = findViewById<TextView>(R.id.textView)
        textView.text = "переданный параметр: $familyName"
    }
}
```
