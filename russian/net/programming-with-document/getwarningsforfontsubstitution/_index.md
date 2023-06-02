---
title: Получить предупреждения о замене шрифта
linktitle: Получить предупреждения о замене шрифта
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать функцию GetWarningsForFontSubstitution в Aspose.PDF для .NET для обнаружения предупреждений о замене шрифта при открытии документа PDF.
type: docs
weight: 190
url: /ru/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF for .NET — это популярная библиотека для работы с PDF, которая позволяет разработчикам создавать, редактировать и преобразовывать PDF-файлы в своих приложениях .NET. Одной из функций, предлагаемых этой библиотекой, является возможность обнаружения предупреждений о замене шрифта при открытии документа PDF. Этот учебник проведет вас через этапы использования`GetWarningsForFontSubstitution` функция Aspose.PDF для .NET для обнаружения предупреждений о замене шрифта при открытии документа PDF.

## Шаг 1: Установите Aspose.PDF для .NET

 Чтобы использовать Aspose.PDF для .NET в ваших .NET-приложениях, вы должны сначала установить библиотеку. Вы можете скачать последнюю версию библиотеки с сайта[Страница загрузки Aspose.PDF для .NET](https://relases.aspose.com/pdf/net).

После загрузки библиотеки извлеките содержимое ZIP-файла в папку на своем компьютере. Затем вам нужно будет добавить ссылку на Aspose.PDF для .NET DLL в ваш проект .NET.

## Шаг 2: Загрузите PDF-документ

 После того, как вы установили Aspose.PDF для .NET и добавили ссылку на DLL в свой проект .NET, вы можете начать использовать`GetWarningsForFontSubstitution` функция обнаружения предупреждений о замене шрифта при открытии документа PDF.

Первым шагом в использовании этой функции является загрузка документа PDF, для которого вы хотите обнаружить предупреждения о замене шрифта. Для этого можно использовать следующий код:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document doc = new Document(dataDir + "input.pdf");
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код загрузит документ PDF в`Document` объект, который затем можно использовать для обнаружения предупреждений о замене шрифта.

## Шаг 3. Обнаружение предупреждений о замене шрифта

Чтобы обнаружить предупреждения о замене шрифта при открытии документа PDF, вы можете использовать следующий код:

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

 В приведенном выше коде`OnFontSubstitution` — это метод, который будет вызываться при обнаружении предупреждения о замене шрифта. Вы можете настроить этот метод для обработки предупреждения о замене шрифта любым удобным для вас способом.

 Вот пример реализации`OnFontSubstitution` метод:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

 В приведенном выше коде`OnFontSubstitution` Метод просто выводит исходное имя шрифта и имя замененного шрифта на консоль всякий раз, когда обнаруживается предупреждение о замене шрифта. Вы можете настроить этот метод для обработки предупреждения о замене шрифта любым удобным для вас способом.

### Пример исходного кода для получения предупреждений о замене шрифта с использованием Aspose.NET для PDF

 Вот полный исходный код для обнаружения предупреждений о замене шрифта при открытии документа PDF с помощью`GetWarningsForFontSubstitution` особенность Aspose.PDF для .NET:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document doc = new Document(dataDir + "input.pdf");

// Обнаружение предупреждений о замене шрифта
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// Обработка предупреждения о замене шрифта
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```