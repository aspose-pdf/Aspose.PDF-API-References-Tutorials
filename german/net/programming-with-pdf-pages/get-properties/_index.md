---
title: PDF-Eigenschaften abrufen
linktitle: PDF-Eigenschaften abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Abrufen von PDF-Eigenschaften wie Boxabmessungen und Drehung mit Aspose.PDF für .NET.
type: docs
weight: 100
url: /de/net/programming-with-pdf-pages/get-properties/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, um die Eigenschaften einer PDF-Datei mithilfe von Aspose.PDF für .NET abzurufen. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.PDF für .NET auf verschiedene Eigenschaften einer PDF-Seite zugreifen, z. B. auf das Grafikfeld, das Zuschneidefeld usw.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Dokumentenverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort der PDF-Datei, deren Eigenschaften Sie abrufen möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Als nächstes müssen Sie das PDF-Dokument mit öffnen`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zur PDF-Datei angeben.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Schritt 3: Greifen Sie auf die Seitensammlung zu
 Jetzt können Sie mit auf die Seitensammlung des Dokuments zugreifen`Pages` Eigentum der`pdfDocument` Objekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Schritt 4: Gehen Sie zu einer bestimmten Seite
Anschließend können Sie mithilfe des Index der Seite in der Sammlung zu einer bestimmten Seite springen. Im folgenden Beispiel greifen wir auf die zweite Seite (Index 1) zu.

```csharp
Page pdfPage = pageCollection[1];
```

## Schritt 5: Seiteneigenschaften abrufen
 Jetzt können Sie die verschiedenen Eigenschaften der PDF-Seite, wie z. B. Grafikfeld, Zuschneidefeld, Zuschneidefeld usw., abrufen, indem Sie die entsprechenden Eigenschaften der Seite verwenden`pdfPage` Objekt.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Beispielquellcode für Get Properties mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Seitensammlung abrufen
PageCollection pageCollection = pdfDocument.Pages;
// Holen Sie sich eine bestimmte Seite
Page pdfPage = pageCollection[1];
// Seiteneigenschaften abrufen
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Abschluss
Herzlichen Glückwunsch! Sie haben die Eigenschaften einer PDF-Datei mit Aspose.PDF für .NET erfolgreich erhalten. Sie haben gelernt, wie Sie ein PDF-Dokument öffnen, zu einer bestimmten Seite navigieren und verschiedene Seiteneigenschaften wie Bemaßungsfelder und Drehung abrufen. Mithilfe dieser Informationen können Sie nun die Handhabung Ihrer PDF-Dateien anhand ihrer Eigenschaften anpassen.

Weitere Informationen zu erweiterten Funktionen und Anpassungsmöglichkeiten finden Sie unbedingt in der offiziellen Dokumentation zu Aspose.PDF für .NET.

### FAQs

#### F: Wie kann ich die Eigenschaften einer PDF-Datei mit Aspose.PDF für .NET abrufen?

A: Um die Eigenschaften einer PDF-Datei mithilfe von Aspose.PDF für .NET abzurufen, können Sie die folgenden Schritte ausführen:

1. Legen Sie das Dokumentverzeichnis fest, indem Sie den Pfad zur PDF-Datei angeben, deren Eigenschaften Sie abrufen möchten.
2.  Öffnen Sie das PDF-Dokument mit`Document` Klasse von Aspose.PDF, die den korrekten Pfad zur PDF-Datei bereitstellt.
3.  Greifen Sie mit auf die Seitensammlung des Dokuments zu`Pages` Eigentum der`pdfDocument` Objekt.
4. Springen Sie mithilfe des Index der Seite in der Sammlung zu einer bestimmten Seite (die Indexierung beginnt bei 1).
5.  Rufen Sie die verschiedenen Eigenschaften der PDF-Seite ab, z. B. ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Seitenzahl und Drehung, indem Sie die entsprechenden Eigenschaften der verwenden`pdfPage` Objekt.

#### F: Welche unterschiedlichen Eigenschaften einer PDF-Seite kann ich mit Aspose.PDF für .NET abrufen?

A: Sie können mit Aspose.PDF für .NET verschiedene Eigenschaften einer PDF-Seite abrufen, wie zum Beispiel:

- ArtBox: Stellt die Abmessungen des Bildmaterials der Seite dar.
- BleedBox: Stellt die Größe des Anschnitts der Seite dar.
- CropBox: Stellt die Abmessungen des sichtbaren Inhalts der Seite nach dem Zuschneiden dar.
- MediaBox: Stellt die Abmessungen der physischen Medien der Seite dar.
- TrimBox: Stellt die Abmessungen des zugeschnittenen Inhalts der Seite dar.
- Rect: Stellt die Abmessungen des Begrenzungsrahmens der Seite dar.
- Seitenzahl: Stellt die Seitenzahl im Dokument dar.
- Drehen: Stellt den Drehwinkel der Seite dar.

#### F: Wie greife ich auf eine bestimmte Seite im PDF-Dokument zu, um deren Eigenschaften abzurufen?

 A: Um auf eine bestimmte Seite im PDF-Dokument zuzugreifen und deren Eigenschaften abzurufen, können Sie die verwenden`Pages` Eigentum der`pdfDocument` -Objekt, um auf die Seitensammlung des Dokuments zuzugreifen. Anschließend können Sie den Index der Seite in der Sammlung verwenden, um zur gewünschten Seite zu springen. Um beispielsweise auf die zweite Seite zuzugreifen, können Sie verwenden`pdfDocument.Pages[1]` (Indizierung beginnt bei 1).

#### F: Kann ich Vorgänge an den abgerufenen Eigenschaften durchführen, z. B. das Ändern oder Ändern der Größe der Seitenfelder?

A: Ja, sobald Sie die Eigenschaften einer PDF-Seite mit Aspose.PDF für .NET abgerufen haben, können Sie verschiedene Vorgänge daran ausführen. Sie können beispielsweise die Abmessungen der Seitenfelder ändern, die Seite drehen oder die abgerufenen Informationen für die benutzerdefinierte Verarbeitung und Bearbeitung des PDF-Dokuments verwenden.

#### F: Unterstützt Aspose.PDF für .NET das Extrahieren von Eigenschaften aus verschlüsselten oder passwortgeschützten PDF-Dateien?

A: Ja, Aspose.PDF für .NET unterstützt das Extrahieren von Eigenschaften aus verschlüsselten oder passwortgeschützten PDF-Dateien. Solange Sie das richtige Passwort zum Öffnen des PDF-Dokuments angeben, können Sie auf seine Eigenschaften zugreifen und diese abrufen, indem Sie den gleichen Ansatz verwenden, der im Tutorial gezeigt wird.