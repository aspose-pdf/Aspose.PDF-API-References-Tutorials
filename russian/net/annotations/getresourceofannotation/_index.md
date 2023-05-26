---
title: Получить ресурс аннотации
linktitle: Получить ресурс аннотации
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как получить ресурс аннотации с помощью Aspose.PDF для .NET с помощью этого пошагового руководства.
type: docs
weight: 90
url: /ru/net/annotations/getresourceofannotation/
---

В примере показано, как получить ресурс аннотации с помощью Aspose.PDF для .NET. Чтобы получить ресурс аннотации с помощью Aspose.PDF для .NET, выполните следующие действия:

## Укажите путь к каталогу, в котором находится документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Откройте документ PDF, содержащий аннотацию, ресурс которой вы хотите получить.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Создайте аннотацию.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Добавьте аннотацию к странице в документе.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Сохраните документ.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Откройте измененный документ.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Получите действие аннотации.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Получите представление действия.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Получите медиа-клип.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Получить спецификацию файла.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Прочтите данные СМИ.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Выведите имя представления и операции представления.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Следуя этим шагам, вы можете легко получить ресурс аннотации в документе PDF, используя Aspose.PDF для .NET.

### Пример исходного кода для получения ресурса аннотации с использованием Aspose.PDF для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Открыть документ
	Document doc = new Document(dataDir + "AddAnnotation.pdf");
	//Создать аннотацию
	ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
	doc.Pages[1].Annotations.Add(sa);
	// Сохранить документ
	doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
	// Открыть документ
	Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
	//Получить действие аннотации
	RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
	//Получить представление действия представления
	Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
	// Медиа-клип
	MediaClip clip = (rendition as MediaRendition).MediaClip;
	FileSpecification data = (clip as MediaClipData).Data;
	MemoryStream ms = new MemoryStream();
	byte[] buffer = new byte[1024];
	int read = 0;
	//Данные носителя доступны в FileSpecification.Contents
	Stream source = data.Contents;
	while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
	{
	ms.Write(buffer, 0, read);
	}
	Console.WriteLine(rendition.Name);
	Console.WriteLine(action.RenditionOperation);

```