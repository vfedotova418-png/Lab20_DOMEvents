# Лабораторная работа №20

ФИО: Федотова Виктория Сергеевна

Группа: ИСП-232

Дата: 17.03.26

---

## Описание

В ходе выполнения данной лабораторной работы было проведено знакомство с объектной моделью документа (DOM) и основами работы с событиями в JavaScript. Были изучены методы поиска HTML-элементов, изменения их содержимого и стилей, а также обработка различных событий пользователя (клик, ввод текста, отправка формы).

## Структура проекта

```
Lab20_DOMO_Events_Fedotova/
│
├── img/
│   ├── gitPushLab20_DOM_Events_Fedotova.png
│   ├── step2_domStructureLab20_Fedotova.png
│   ├── step3_domSelectionLab20_Fedotova.png
│   ├── step4_domManipulationLab20_Fedotova.png
│   ├── step5_clickEventLab20_Fedotova.png
│   ├── step6_inputEventListener_Fedotova.png
│   ├── step7_miniTaskLab20_Fedotova.png
│   ├── step8_formInputLab20_Fedotova.png
│   ├── step9_formValidationLab20_Fedotova.png
│   └── step10_dynamicElementsLab20_Fedotova.png
│
├── index.html
├── main.js
├── dynamicElements.html
├── dynamicElements.js
└── README.md
```

## Сравнение с C# (WinForms/WPF)

**DOM в JS = Controls в C# WinForms**

|      Концепция       |                C# (WinForms)                |                   JavaScript (DOM)                   |
| :------------------: | :-----------------------------------------: | :--------------------------------------------------: |
|    Найти элемент     | Button myButton = this.Controls["myButton"] | const myButton = document.getElementById("myButton") |
|    Изменить текст    |         label1.Text = "Новый текст"         |          label1.textContent = "Новый текст"          |
| Добавить обработчик  |        button1.Click += HandleClick         |    button.addEventListener("click", handleClick)     |
|   Создать элемент    |          Button btn = new Button()          |     const btn = document.createElement("button")     |
| Добавить в контейнер |          panel1.Controls.Add(btn)           |                panel.appendChild(btn)                |
|    Скрыть элемент    |           button1.Visible = false           |            button.style.display = "none"             |

**Events в JS = События в C#**

C# (WinForms):

```c#
private void Button1_Click(object sender, EventArgs e) {
    label1.Text = "Нажато!";
}
```

JavaScript (DOM):

```JavaScript
button.addEventListener("click", (e) => {
    label.textContent = "Нажато!";
});
```

**Валидация формы**

C# (WinForms):

```c#
private void SubmitButton_Click(object sender, EventArgs e) {
    if (string.IsNullOrEmpty(nameTextBox.Text)) {
        MessageBox.Show("Введите имя!");
        return;
    }
    // ...
}
```

JavaScript (DOM):

```JavaScript
form.addEventListener("submit", (e) => {
    e.prevemtDefault();

    if (!nameInput.value.trim()) {
        alert("Введите имя!");
        return;
    }
    // ...
});
```

#### Главные отличия:

|   Аспект    |     C# WinForms     |   JavaScript DOM    |
| :---------: | :-----------------: | :-----------------: |
| Компиляция  |         Да          | Нет (интерпретация) |
|  Типизация  |       Строгая       |    Динамическая     |
|   Ошибки    | Во время компиляции | Во время выполнения |
| UI-дизайнер |  Есть (визуальный)  |  Нет (только код)   |
|  Платформа  |       Windows       |    Любой браузер    |

#### Преимущества DOM перед WinForms:

- Кроссплатформенность (работает везде)
- Не нужна установка приложения
- Легко обновлять (обновил файлы - всё работает)
- Современные UI (CSS, анимации)

#### Преимущества WinForms перед DOM:

- Визуальный дизайнер (drag & drop)
- Ошибки на этапе компиляции
- Интеграция с Windows API
- Более понятная структура

**Вывод:** DOM и WinForms решают схожие задачи, но разными подходами
