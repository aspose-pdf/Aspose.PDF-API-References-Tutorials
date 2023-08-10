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

## Шаг 1: Укажите путь к каталогу, в котором находится документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте документ PDF, содержащий аннотацию, ресурс которой вы хотите получить.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Шаг 3: Создайте аннотацию.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Шаг 4: Добавьте аннотацию на страницу документа.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Шаг 5: Сохраните документ.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Шаг 6: Откройте измененный документ.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Шаг 7: Получите действие аннотации.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Шаг 7: Получите представление действия.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Шаг 8: Получите медиа-клип.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Шаг 9: Получите спецификацию файла.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Шаг 10: Считайте данные носителя.

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

## Шаг 11: Напечатайте имя представления и операцию воспроизведения.

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

## Заключение

В этом руководстве мы рассмотрели, как получить ресурс определенной аннотации из документа PDF с помощью Aspose.PDF для .NET. Следуя пошаговому руководству и используя предоставленный исходный код C#, разработчики могут легко получать доступ и управлять аннотациями, включая аннотации представления, в своих PDF-документах.

### Часто задаваемые вопросы

#### Вопрос. Что такое представление в контексте аннотаций PDF?

О: В контексте аннотаций PDF воспроизведение — это презентация мультимедийного содержимого. Это позволяет встраивать мультимедиа, например аудио или видео, в документ PDF. В аннотации представления указывается, какие медиаданные должны быть представлены и как их следует воспроизводить.

#### Вопрос. Можно ли получить имя медиафайла, связанного с аннотацией воспроизведения?

 О: Да, вы можете получить имя медиафайла, связанного с аннотацией воспроизведения, с помощью Aspose.PDF для .NET. Доступ к имени медиафайла можно получить через`FileSpecification` принадлежащий`MediaClip` объект.

#### Вопрос: Может ли Aspose.PDF для .NET извлекать медиафайлы из аннотаций воспроизведения?

О: Да, Aspose.PDF для .NET может извлекать медиаданные из аннотаций воспроизведения, которые включают аудио- или видеоконтент, и сохранять их в виде отдельного файла.

#### Вопрос. Как получить доступ к медиаданным аннотации воспроизведения?

 A: Медиаданные аннотации воспроизведения могут быть доступны через`FileSpecification.Contents` собственность`MediaClipData` объект.

#### Вопрос. Можно ли изменить носитель, связанный с аннотацией воспроизведения, с помощью Aspose.PDF для .NET?

О: Aspose.PDF для .NET предоставляет методы для доступа и изменения мультимедийных данных, связанных с аннотацией воспроизведения. Вы можете обновить или заменить файл мультимедиа, используемый аннотацией к воспроизведению.