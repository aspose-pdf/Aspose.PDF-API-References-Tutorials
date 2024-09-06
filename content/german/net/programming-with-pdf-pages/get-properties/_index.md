---
title: PDF-Eigenschaften abrufen
linktitle: PDF-Eigenschaften abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Abrufen von PDF-Eigenschaften wie Boxabmessungen und Drehung mit Aspose.PDF für .NET.
type: docs
weight: 100
url: /de/net/programming-with-pdf-pages/get-properties/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, um die Eigenschaften einer PDF-Datei mit Aspose.PDF für .NET abzurufen. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mit Aspose.PDF für .NET auf verschiedene Eigenschaften einer PDF-Seite wie Art Box, Crop Box, Crop Box usw. zugreifen können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort der PDF-Datei, deren Eigenschaften Sie abrufen möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Als nächstes müssen Sie das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Achten Sie darauf, den richtigen Pfad zur PDF-Datei anzugeben.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Schritt 3: Zugriff auf die Seitensammlung
 Jetzt können Sie auf die Seitensammlung des Dokuments zugreifen über`Pages` Eigentum der`pdfDocument` Objekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Schritt 4: Gehen Sie zu einer bestimmten Seite
Anschließend können Sie über den Index der Seite in der Sammlung zu einer bestimmten Seite springen. Im folgenden Beispiel greifen wir auf die zweite Seite zu (Index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Schritt 5: Seiteneigenschaften abrufen
 Jetzt können Sie die verschiedenen Eigenschaften der PDF-Seite, wie Art-Box, Crop-Box, Crop-Box usw., abrufen, indem Sie die entsprechenden Eigenschaften der`pdfPage` Objekt.

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

### Beispielquellcode für „Get Properties“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Seitensammlung abrufen
PageCollection pageCollection = pdfDocument.Pages;
// Bestimmte Seite abrufen
Page pdfPage = pageCollection[1];
// Abrufen von Seiteneigenschaften
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
Herzlichen Glückwunsch! Sie haben die Eigenschaften einer PDF-Datei erfolgreich mit Aspose.PDF für .NET abgerufen. Sie haben gelernt, wie Sie ein PDF-Dokument öffnen, zu einer bestimmten Seite navigieren und verschiedene Seiteneigenschaften wie Dimensionsfelder und Drehung abrufen. Sie können diese Informationen nun verwenden, um die Handhabung Ihrer PDF-Dateien basierend auf ihren Eigenschaften anzupassen.

Weitere Informationen zu erweiterten Funktionen und Anpassungsmöglichkeiten finden Sie in der offiziellen Aspose.PDF-Dokumentation für .NET.

### Häufig gestellte Fragen

#### F: Wie kann ich die Eigenschaften einer PDF-Datei mit Aspose.PDF für .NET abrufen?

A: Um die Eigenschaften einer PDF-Datei mit Aspose.PDF für .NET abzurufen, können Sie die folgenden Schritte ausführen:

1. Legen Sie das Dokumentverzeichnis fest, indem Sie den Pfad zur PDF-Datei angeben, deren Eigenschaften Sie abrufen möchten.
2.  Öffnen Sie das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF, die den richtigen Pfad zur PDF-Datei bereitstellt.
3.  Greifen Sie auf die Seitensammlung des Dokuments zu, indem Sie`Pages` Eigentum der`pdfDocument` Objekt.
4. Springen Sie zu einer bestimmten Seite, indem Sie den Index der Seite in der Sammlung verwenden (die Indizierung beginnt bei 1).
5.  Rufen Sie die verschiedenen Eigenschaften der PDF-Seite, wie ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Seitenzahl und Rotation, mithilfe der entsprechenden Eigenschaften des`pdfPage` Objekt.

#### F: Welche verschiedenen Eigenschaften einer PDF-Seite kann ich mit Aspose.PDF für .NET abrufen?

A: Mit Aspose.PDF für .NET können Sie verschiedene Eigenschaften einer PDF-Seite abrufen, beispielsweise:

- ArtBox: Stellt die Abmessungen des Bildmaterials der Seite dar.
- BleedBox: Stellt die Abmessungen des Anschnitts der Seite dar.
- CropBox: Stellt die Abmessungen des sichtbaren Seiteninhalts nach dem Zuschneiden dar.
- MediaBox: Stellt die Abmessungen des physischen Mediums der Seite dar.
- TrimBox: Stellt die Abmessungen des zugeschnittenen Seiteninhalts dar.
- Rechteck: Stellt die Abmessungen des Begrenzungsrahmens der Seite dar.
- Seitenzahl: Stellt die Seitenzahl im Dokument dar.
- Drehen: Stellt den Drehwinkel der Seite dar.

#### F: Wie greife ich auf eine bestimmte Seite im PDF-Dokument zu, um ihre Eigenschaften abzurufen?

 A: Um auf eine bestimmte Seite im PDF-Dokument zuzugreifen und deren Eigenschaften abzurufen, können Sie das`Pages` Eigentum der`pdfDocument` Objekt, um auf die Seitensammlung des Dokuments zuzugreifen. Anschließend können Sie den Index der Seite in der Sammlung verwenden, um zur gewünschten Seite zu springen. Um beispielsweise auf die zweite Seite zuzugreifen, können Sie Folgendes verwenden:`pdfDocument.Pages[1]` (Die Indizierung beginnt bei 1).

#### F: Kann ich mit den abgerufenen Eigenschaften Vorgänge ausführen, z. B. die Seitenfelder ändern oder ihre Größe anpassen?

A: Ja, wenn Sie die Eigenschaften einer PDF-Seite mit Aspose.PDF für .NET abrufen, können Sie verschiedene Vorgänge damit durchführen. Sie können beispielsweise die Abmessungen der Seitenfelder ändern, die Seite drehen oder die abgerufenen Informationen zur benutzerdefinierten Verarbeitung und Bearbeitung des PDF-Dokuments verwenden.

#### F: Unterstützt Aspose.PDF für .NET das Extrahieren von Eigenschaften aus verschlüsselten oder kennwortgeschützten PDF-Dateien?

A: Ja, Aspose.PDF für .NET unterstützt das Extrahieren von Eigenschaften aus verschlüsselten oder kennwortgeschützten PDF-Dateien. Solange Sie zum Öffnen des PDF-Dokuments das richtige Kennwort eingeben, können Sie mit demselben im Tutorial gezeigten Ansatz auf dessen Eigenschaften zugreifen und diese abrufen.