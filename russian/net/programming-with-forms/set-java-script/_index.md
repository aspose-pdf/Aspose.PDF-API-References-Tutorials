---
title: Установить Java-скрипт
linktitle: Установить Java-скрипт
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для установки JavaScript в полях формы в файлах PDF.
type: docs
weight: 270
url: /ru/net/programming-with-forms/set-java-script/
---

В этом руководстве мы шаг за шагом объясним, как использовать библиотеку Aspose.PDF для .NET для определения JavaScript в поле формы документа PDF. Мы покажем вам, как настроить действия JavaScript для выполнения определенных операций с текстовым полем.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Среда разработки .NET, установленная в вашей системе.
- Библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## Шаг 1. Настройка каталога документов

 Первый шаг — настроить каталог документов, в котором находится файл PDF, с которым вы хотите работать. Вы можете использовать`dataDir`переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2: Загрузка входного PDF-файла

 На этом шаге мы загрузим входной PDF-файл, используя`Document`класс Aspose.PDF.

```csharp
// Загрузить исходный PDF-файл
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Убедитесь, что входной файл PDF находится в указанной папке документов.

## Шаг 3. Доступ к полю TextBox

 Чтобы применить JavaScript к определенному текстовому полю, нам сначала нужно получить доступ к этому полю. В этом примере мы предполагаем, что текстовое поле называется «textbox1». Использовать`doc.Form["textbox1"]` метод получения соответствующего`TextBoxField` объект.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Убедитесь, что указанное текстовое поле существует во входном файле PDF.

## Шаг 4. Настройте действия JavaScript

 Теперь, когда мы получили доступ к текстовому полю, мы можем настроить действия JavaScript, связанные с этим полем. В этом примере мы будем использовать два действия:`OnModifyCharacter` и`OnFormat` . Эти действия будут определены с помощью`JavascriptAction` объекты.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Обязательно настройте действия JavaScript в соответствии с вашими потребностями.

## Шаг 5: Установка начального значения поля

Перед сохранением полученного PDF-файла мы можем установить начальное значение для текстового поля. В этом примере мы установим для поля значение «123».

```csharp
field.Value = "123";
```

Настройте это значение в соответствии с вашими потребностями.

## Шаг 6: Сохранение полученного PDF-файла

 Теперь, когда мы закончили настройку текстового поля и действий JavaScript, мы можем сохранить полученный PDF-файл, используя команду`Save` метод`Document` сорт.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Сохраните полученный PDF
doc.Save(dataDir);
```

Обязательно укажите полный путь и имя файла для полученного PDF-файла.


### Пример исходного кода для Set Java Script с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить исходный PDF-файл
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 цифры после точки
// Без разделителя
// Нег стиль = минус
// Нет валюты
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Установить начальное значение поля
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Сохранить полученный PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как использовать библиотеку Aspose.PDF для .NET для установки JavaScript в поле формы документа PDF. Следуя описанным шагам, вы можете настроить действия JavaScript для выполнения различных операций с текстовыми полями. Изучите возможности Aspose.PDF для .NET, чтобы расширить возможности работы с PDF-файлами.