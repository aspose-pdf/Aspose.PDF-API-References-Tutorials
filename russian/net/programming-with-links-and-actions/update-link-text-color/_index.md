---
title: Обновить цвет текста ссылки
linktitle: Обновить цвет текста ссылки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как обновить цвет текста ссылок в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-links-and-actions/update-link-text-color/
---

Из этого пошагового руководства вы узнаете, как обновить цвет текста ссылок в файле PDF с помощью Aspose.PDF для .NET.

## Шаг 1. Настройка среды

Убедитесь, что вы настроили среду разработки с проектом C# и соответствующими ссылками на Aspose.PDF.

## Шаг 2: Загрузка файла PDF

Установите путь к каталогу ваших документов и загрузите файл PDF, используя следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите PDF-файл
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Шаг 3: Навигация по аннотациям ссылок

Прокрутите все аннотации ссылок на второй странице документа, используя следующий код:

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // Найдите текст под аннотацией
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // Изменить цвет текста.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## Шаг 4. Сохраните документ с обновленным текстом ссылки

 Сохраните документ с обновленным текстом ссылки, используя`Save` метод:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## Шаг 5: Отображение результата

Вывести сообщение об успешном обновлении цвета текста аннотации ссылки и указать расположение сохраненного файла:

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### Пример исходного кода для обновления цвета текста ссылки с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// Поиск текста под аннотацией
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// Изменить цвет текста.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// Сохраните документ с обновленной ссылкой
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

Поздравляем! Теперь вы знаете, как обновить цвет текста ссылок в файле PDF с помощью Aspose.PDF для .NET. Используйте эти знания, чтобы настроить внешний вид ваших ссылок в документах PDF.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.