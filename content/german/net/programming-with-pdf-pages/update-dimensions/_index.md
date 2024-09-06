---
title: PDF-Seitenabmessungen aktualisieren
linktitle: PDF-Seitenabmessungen aktualisieren
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Aktualisieren der PDF-Seitenabmessungen mit Aspose.PDF für .NET. Überprüfen Sie die Abmessungen entsprechend Ihren Anforderungen.
type: docs
weight: 150
url: /de/net/programming-with-pdf-pages/update-dimensions/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Aktualisieren der Seitenabmessungen in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Seitenabmessungen in einem PDF-Dokument mit Aspose.PDF für .NET ändern.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Dokumentverzeichnis festlegen
Zunächst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes PDF-Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Anschließend können Sie das bestehende PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Schritt 3: Holen Sie sich die Seitensammlung
 Nun können Sie auf die Seitensammlung des PDF-Dokuments zugreifen über`Pages` Eigentum der`Document` Klasse.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Schritt 4: Eine bestimmte Seite abrufen
Anschließend können Sie eine bestimmte Seite des Dokuments über den Index der Seite in der Sammlung auswählen. In diesem Beispiel verwenden wir die zweite Seite (Index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Schritt 5: Definieren Sie die neuen Seitenabmessungen
 Nun können Sie die neue Seitengröße über die`SetPageSize()` Methode der`Page`Objekt. In diesem Beispiel legen wir die Seitenabmessungen auf A4 (11,7 x 8,3 Zoll) fest, umgerechnet in Punkte (1 Zoll = 72 Punkte).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Schritt 6: Speichern Sie das aktualisierte Dokument
 Abschließend können Sie das aktualisierte PDF-Dokument in einer Datei speichern mit dem`Save()` Methode der`Document`Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für Update Dimensions mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Seitensammlung abrufen
PageCollection pageCollection = pdfDocument.Pages;
// Bestimmte Seite abrufen
Page pdfPage = pageCollection[1];
// Stellen Sie die Seitengröße auf A4 (11,7 x 8,3 Zoll) ein und in Aspose.Pdf ist 1 Zoll = 72 Punkte
// Die Abmessungen des A4-Formats in Punkten betragen also (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Speichern des aktualisierten Dokuments
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Abmessungen einer Seite in einem PDF-Dokument mit Aspose.PDF für .NET aktualisiert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Abmessungen einer Seite in einem PDF-Dokument ganz einfach nach Bedarf ändern. Aspose.PDF bietet eine leistungsstarke und flexible API für die Arbeit mit PDF-Dateien und die Durchführung verschiedener Manipulationen, einschließlich der Änderung der Seitenabmessungen. Mit diesem Wissen können Sie die Abmessungen Ihrer PDF-Seiten steuern und anpassen, um sie Ihren spezifischen Anforderungen anzupassen.

### FAQs zum Aktualisieren der PDF-Seitenabmessungen

#### F: Wie kann ich mit Aspose.PDF für .NET die Abmessungen einer bestimmten Seite in einem PDF-Dokument aktualisieren?

A: Um die Abmessungen einer bestimmten Seite in einem PDF-Dokument mit Aspose.PDF für .NET zu aktualisieren, können Sie diese Schritte ausführen:

1. Legen Sie das Dokumentverzeichnis fest, indem Sie den Pfad angeben, in dem sich Ihre ursprüngliche PDF-Datei befindet und in dem Sie die aktualisierte PDF-Datei speichern möchten. Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad.
2.  Öffnen Sie das vorhandene PDF-Dokument zur Aktualisierung mit dem`Document` Klasse von Aspose.PDF. Achten Sie darauf, den richtigen Pfad zum ursprünglichen PDF-Dokument anzugeben.
3.  Zugriff auf die Seitensammlung des PDF-Dokuments über den`Pages` Eigentum der`Document` Klasse.
4. Wählen Sie die Seite, die Sie aktualisieren möchten, aus der Seitensammlung aus, indem Sie den Index der Seite verwenden. Im bereitgestellten C#-Quellcode verwenden wir die zweite Seite (Index 1).
5.  Definieren Sie die neue Seitengröße mit dem`SetPageSize()` Methode der`Page` Objekt. Im Beispiel haben wir die Seitenmaße auf die Größe A4 (11,7 x 8,3 Zoll) eingestellt, umgerechnet in Punkt (1 Zoll = 72 Punkt).
6.  Speichern Sie das aktualisierte PDF-Dokument in einer Datei mit dem`Save()` Methode der`Document`Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

#### F: Kann ich die Abmessungen mehrerer Seiten im PDF-Dokument gleichzeitig aktualisieren?

A: Ja, Sie können den bereitgestellten Quellcode ändern, um die Abmessungen mehrerer Seiten im PDF-Dokument gleichzeitig zu aktualisieren. Anstatt eine bestimmte Seite auszuwählen (wie in Schritt 4 gezeigt), können Sie alle Seiten in der Seitensammlung durchlaufen und für jede Seite die gewünschte Seitengröße festlegen.

#### F: Wie konvertiere ich Seitenmaße von Zoll in Punkte, wenn ich Aspose.PDF für .NET verwende?

 A: In Aspose.PDF für .NET ist die Maßeinheit für Seitenabmessungen Punkte, wobei 1 Zoll 72 Punkten entspricht. Um Zoll in Punkte umzurechnen, können Sie die folgende Formel verwenden:`points = inches * 72`. Um beispielsweise eine Seitengröße von 11,7 x 8,3 Zoll festzulegen, können Sie die entsprechenden Abmessungen in Punkten als (11,7 * 72) und (8,3 * 72) berechnen.

#### F: Hat die Aktualisierung der Seitenabmessungen Auswirkungen auf das Inhaltslayout des PDF-Dokuments?

A: Ja, das Aktualisieren der Abmessungen einer Seite wirkt sich auf das Inhaltslayout des PDF-Dokuments auf dieser bestimmten Seite aus. Wenn Sie die Seitenabmessungen ändern, wird der Inhalt auf der Seite entsprechend angepasst, damit er in die neuen Abmessungen passt.

#### F: Ist es möglich, die Änderungen rückgängig zu machen und nach der Aktualisierung die ursprünglichen Seitenabmessungen wiederherzustellen?

A: Ja, wenn Sie die Änderungen rückgängig machen und die ursprünglichen Seitenabmessungen wiederherstellen möchten, können Sie entweder eine Kopie des ursprünglichen PDF-Dokuments aufbewahren, bevor Sie Änderungen vornehmen, oder das ursprüngliche PDF-Dokument erneut öffnen, ohne die Änderungen zu speichern. Auf diese Weise bleiben die ursprünglichen Abmessungen erhalten.