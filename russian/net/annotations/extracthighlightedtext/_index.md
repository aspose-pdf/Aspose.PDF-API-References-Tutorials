---
title: Извлечь выделенный текст
linktitle: Извлечь выделенный текст
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь выделенный текст с помощью Aspose.PDF для .NET с помощью этого пошагового руководства.
type: docs
weight: 60
url: /ru/net/annotations/extracthighlightedtext/
---
Чтобы извлечь выделенный текст из документа PDF, вы можете использовать Aspose.PDF для .NET API. Этот API предоставляет простой способ получить весь выделенный текст в документе.

## Шаг 1. Загрузите PDF-документ

 Первым шагом в извлечении выделенного текста из документа PDF является загрузка документа с помощью API Aspose.PDF для .NET. Вы можете сделать это, создав новый экземпляр`Document` class и передавая путь к PDF-документу в качестве параметра. 

```csharp
// Путь к каталогу документов.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Шаг 2. Переберите все аннотации

 Следующим шагом будет просмотр всех аннотаций в документе PDF. Вы можете сделать это с помощью`foreach` петля, вот так:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Код идет здесь
}
```

## Шаг 3. Отфильтруйте аннотации текстовой разметки

 Внутри`foreach` цикла, вам нужно будет отфильтровать все аннотации, которые не являются аннотациями текстовой разметки. Вы можете сделать это, проверив, является ли аннотация экземпляром`TextMarkupAnnotation` сорт.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Код идет здесь
}
```

## Шаг 4: Извлеките выделенные фрагменты текста

 После того, как вы отфильтровали все аннотации текстовой разметки, вы можете получить выделенные фрагменты текста для каждой аннотации. Вы можете сделать это, позвонив в`GetMarkedTextFragments()` метод на`TextMarkupAnnotation` объект.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Шаг 5: Отобразите выделенный текст

 Наконец, вы можете отобразить выделенный текст пользователю. Вы можете сделать это, перебирая каждый`TextFragment` объект в`TextFragmentCollection` и вызов`Text` свойство.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Пример исходного кода для извлечения выделенного текста с использованием Aspose.PDF для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir ="YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is TextMarkupAnnotation)
		{
			TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
			TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
			foreach (TextFragment tf in collection)
			{
				Console.WriteLine(tf.Text);
			}
		}
	}
```

