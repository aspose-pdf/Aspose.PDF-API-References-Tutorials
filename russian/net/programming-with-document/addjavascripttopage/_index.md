---
title: Добавить Java-скрипт на страницу
linktitle: Добавить Java-скрипт на страницу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить JavaScript в файлы PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с учебными пособиями по коду для сценариев на уровне документов и страниц.
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

```csharp
            
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующие файлы PDF
Document doc = new Document(dataDir + "input.pdf");

// Добавление JavaScript на уровне документа
//Создание экземпляра JavascriptAction с требуемым оператором JavaScript
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


