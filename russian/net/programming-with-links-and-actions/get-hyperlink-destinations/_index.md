---
title: Получить назначения гиперссылок
linktitle: Получить назначения гиперссылок
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь места назначения гиперссылок из файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF для .NET — это мощная библиотека для обработки и извлечения информации из PDF-файлов с использованием языка программирования C#. В этом руководстве мы сосредоточимся на извлечении пунктов назначения гиперссылок из файла PDF с помощью Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Интегрированная среда разработки (IDE), такая как Visual Studio.
- Библиотека Aspose.PDF для .NET, установленная на вашем компьютере.

## Шаг 1: Настройка среды разработки

Прежде чем приступить к написанию кода, вам необходимо настроить среду разработки, создав новый проект C# в вашей любимой среде IDE.

## Шаг 2: Импортируйте ссылки на Aspose.PDF

Чтобы использовать Aspose.PDF для .NET, вам необходимо добавить соответствующие ссылки в ваш проект. Выполните следующие шаги, чтобы импортировать необходимые ссылки:

1. В своем проекте щелкните правой кнопкой мыши «Ссылки» и выберите «Добавить ссылку».
2. В окне «Добавить ссылку» найдите и выберите файлы DLL Aspose.PDF для .NET.
3. Нажмите «ОК», чтобы импортировать ссылки в ваш проект.

## Шаг 3: Загрузка файла PDF

Прежде чем вы сможете извлечь места назначения гиперссылок, вы должны загрузить PDF-файл в свое приложение. Используйте следующий код для загрузки файла PDF:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите PDF-файл
Document document = new Document(dataDir + "input.pdf");
```

Обязательно укажите правильный путь к каталогу документов и файлу PDF, который вы хотите обработать.

## Шаг 4. Навигация по страницам документа

Теперь, когда файл PDF загружен, вам нужно просмотреть все страницы документа. Это позволит вам получить

ir аннотации гиперссылок, присутствующие на каждой странице. Используйте следующий код для перебора страниц документа:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Получить аннотации ссылок определенной страницы
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Создайте список для хранения всех ссылок
     IList<Annotation> list = selector. Selected;
     // Перебрать каждый элемент в списке
     foreach(LinkAnnotation a in list)
     {
         // Распечатать целевой URL
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Этот код перебирает каждую страницу документа и выбирает аннотации гиперссылок, присутствующие на каждой странице. Затем он сохраняет эти аннотации в списке и печатает целевой URL для каждой ссылки.

## Шаг 5: Получение адресатов гиперссылок

Последним шагом является извлечение адресатов гиперссылок из аннотаций гиперссылок. Следующий код показывает, как это сделать:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Используйте пункт назначения по своему усмотрению
     }
}
```

В этом коде мы получаем каждое назначение гиперссылки из аннотаций ссылки и сохраняем назначение в переменной. Затем вы можете использовать это назначение по своему усмотрению в своем приложении.

### Пример исходного кода для получения пунктов назначения гиперссылок с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document document = new Document(dataDir + "input.pdf");
	// Пройтись по всей странице PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Получить аннотации ссылок с определенной страницы
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Создать список, содержащий все ссылки
		IList<Annotation> list = selector.Selected;
		// Итерация по элементу invidiaul внутри списка
		foreach (LinkAnnotation a in list)
		{
			// Распечатать целевой URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```