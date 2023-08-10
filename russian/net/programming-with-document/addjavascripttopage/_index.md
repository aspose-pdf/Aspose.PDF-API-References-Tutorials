---
title: Добавить Java-скрипт в PDF-файл
linktitle: Добавить PDF-файл Java Script
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить JavaScript в файл PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с учебными пособиями по коду для сценариев на уровне документов и страниц.
type: docs
weight: 10
url: /ru/net/programming-with-document/addjavascripttopage/
---
Чтобы добавить JavaScript в файл PDF, мы будем использовать Aspose.PDF для .NET. Эта библиотека предоставляет простой и эффективный способ работы с файлами PDF в приложениях .NET. Следующие шаги проведут вас через процесс добавления JavaScript в файл PDF с помощью Aspose.PDF для .NET.

## Шаг 1: Загрузите файл PDF

 Первый шаг — загрузить PDF-файл, в который вы хотите добавить JavaScript. Вы можете сделать это с помощью`Document` класс, предоставляемый Aspose.PDF для .NET.`Document` Класс предоставляет методы для загрузки, сохранения и управления PDF-файлами.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующие файлы PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 2. Добавьте JavaScript на уровне документа

Чтобы добавить JavaScript на уровне документа, мы будем использовать`JavascriptAction` класс, предоставляемый Aspose.PDF для .NET. Этот класс позволяет вам указать оператор JavaScript, который вы хотите добавить в файл PDF.

```csharp
// Добавление JavaScript на уровне документа
// Создайте экземпляр JavascriptAction с желаемым оператором JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Назначьте объект JavascriptAction желаемому действию документа
doc.OpenAction = javaScript;
```

В этом руководстве мы добавляем оператор JavaScript, который будет печатать PDF-файл с указанными параметрами при открытии документа.

## Шаг 3. Добавьте JavaScript на уровне страницы

 Чтобы добавить JavaScript на уровне страницы, мы будем использовать`JavascriptAction` класс и`Actions` свойство, предоставленное Aspose.PDF для .NET. Это свойство позволяет указать операторы JavaScript, которые будут выполняться при открытии или закрытии страницы.

```csharp
// Добавление JavaScript на уровне страницы
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

В этом руководстве мы добавляем операторы JavaScript, которые будут отображать предупреждающее сообщение при открытии или закрытии страницы.

## Шаг 4: Сохраните файл PDF

После того, как вы добавили JavaScript в файл PDF, вам необходимо сохранить измененный файл. Вы можете сделать это с помощью`Save` метод, предоставляемый`Document` сорт.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Этот код сохранит измененный файл PDF в указанный каталог.

### Пример исходного кода для добавления сценария Java на страницу с использованием Aspose.PDF для .NET

```csharp
            
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующие файлы PDF
Document doc = new Document(dataDir + "input.pdf");

// Добавление JavaScript на уровне документа
// Создание экземпляра JavascriptAction с требуемым оператором JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Назначьте объект JavascriptAction желаемому действию документа
doc.OpenAction = javaScript;

// Добавление JavaScript на уровне страницы
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Заключение

В этой статье мы объяснили, как добавить JavaScript в файл PDF как на уровне документа, так и на уровне страницы, используя Aspose.PDF для .NET. Мы предоставили пошаговые инструкции и включили полный исходный код для каждого примера. Обладая этими знаниями, вы можете добавлять JavaScript в свои PDF-файлы и настраивать их поведение в соответствии со своими потребностями.


### Часто задаваемые вопросы по добавлению java-скрипта в файл PDF

#### В: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам работать с файлами PDF в приложениях .NET. Он предоставляет широкий спектр функций для создания, изменения и управления PDF-документами.

#### В: Могу ли я добавить JavaScript в документ PDF, используя Aspose.PDF для .NET?

О: Да, Aspose.PDF для .NET позволяет добавлять JavaScript как на уровень документа, так и на уровень страницы файла PDF, позволяя создавать динамические и интерактивные документы PDF.

#### В: Как загрузить существующий файл PDF с помощью Aspose.PDF для .NET?

 О: Вы можете загрузить существующий файл PDF, используя`Document` класс и его методы, как показано в пошаговом руководстве.

#### В: Какие типы действий JavaScript я могу добавить в документ PDF?

О: С помощью Aspose.PDF для .NET вы можете добавить широкий спектр действий JavaScript, таких как печать, предупреждающие сообщения, манипулирование полями формы и многое другое.

#### В: Подходит ли Aspose.PDF для .NET для коммерческих проектов?

О: Да, Aspose.PDF для .NET — это надежная и надежная библиотека, которая обычно используется в коммерческих проектах для задач обработки и создания PDF-файлов.

