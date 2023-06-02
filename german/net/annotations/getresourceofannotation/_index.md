---
title: Holen Sie sich eine Anmerkungsressource
linktitle: Holen Sie sich eine Anmerkungsressource
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie die Ressource einer Anmerkung mit Aspose.PDF für .NET abrufen.
type: docs
weight: 90
url: /de/net/annotations/getresourceofannotation/
---

Das Beispiel zeigt, wie man mit Aspose.PDF für .NET eine Annotationsressource erhält. Um die Ressource einer Anmerkung mit Aspose.PDF für .NET abzurufen, führen Sie die folgenden Schritte aus:

## Schritt 1: Legen Sie den Pfad des Verzeichnisses fest, in dem sich das Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument, das die Anmerkung enthält, deren Ressource Sie erhalten möchten.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Schritt 3: Erstellen Sie eine Anmerkung.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Schritt 4: Fügen Sie die Anmerkung zu einer Seite im Dokument hinzu.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Schritt 5: Speichern Sie das Dokument.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Schritt 6: Öffnen Sie das geänderte Dokument.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Schritt 7: Rufen Sie die Aktion der Anmerkung ab.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Schritt 7: Holen Sie sich die Darstellung der Aktion.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Schritt 8: Holen Sie sich den Medienclip.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Schritt 9: Holen Sie sich die Dateispezifikation.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Schritt 10: Lesen Sie die Daten des Mediums.

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

## Schritt 11: Drucken Sie den Namen der Wiedergabe und des Wiedergabevorgangs aus.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF für .NET ganz einfach die Ressource einer Anmerkung in einem PDF-Dokument abrufen.

### Beispielquellcode für Get Resource Of Annotation mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Anmerkung erstellen
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Dokument speichern
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Dokument öffnen
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Aktion der Anmerkung abrufen
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Rufen Sie die Wiedergabe der Wiedergabeaktion ab
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Medienclip
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Auf Mediendaten kann in FileSpecification.Contents zugegriffen werden
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```