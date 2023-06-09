---
title: Dimensionen abrufen
linktitle: Dimensionen abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: In diesem Tutorial erklären wir, wie Sie mit Aspose.PDF für .NET PDF-Seitenabmessungen erhalten und Manipulationen durchführen. Es werden detaillierte Schritte bereitgestellt, die Sie durch den Prozess führen.
type: docs
weight: 60
url: /de/net/programming-with-pdf-pages/get-dimensions/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Abrufen von Seitenabmessungen in einer PDF-Datei mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.PDF für .NET die Abmessungen einer Seite in einer PDF-Datei ermitteln.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort, an dem sich Ihre PDF-Datei befindet. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Anschließend können Sie die PDF-Datei mit öffnen`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zur PDF-Datei angeben.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Schritt 3: Fügen Sie eine leere Seite hinzu (falls erforderlich)
Wenn das PDF-Dokument bereits Seiten enthält, können Sie über den Index zu einer vorhandenen Seite springen`1` (Die erste Seite hat einen Index von 1). Andernfalls können Sie dem Dokument eine neue Seite hinzufügen.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Schritt 4: Seitenabmessungen ermitteln
 Sie können jetzt die Seitenabmessungen mithilfe von ermitteln`GetPageRect()` Methode der`Page` Objekt. Diese Methode gibt a zurück`Rectangle` Objekt, das die Abmessungen der Seite enthält. Auf die Breite und Höhe können Sie über zugreifen`Width` Und`Height` Eigenschaften.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Schritt 5: Drehen Sie die Seite
 Wenn Sie die Seite drehen möchten, können Sie die verwenden`Rotate` Eigentum der`Page` Objekt. In diesem Beispiel wird die Seite um 90 Grad gedreht.

```csharp
page. Rotate = Rotate. on90;
```

## Schritt 6: Ermitteln Sie die Seitenabmessungen erneut
 Nach der Seitendrehung können Sie die Seitenabmessungen mithilfe von erneut abrufen`GetPageRect()` Methode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Beispielquellcode für Get Dimensions mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Fügt dem PDF-Dokument eine leere Seite hinzu
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Informationen zur Seitenhöhe und -breite abrufen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Seite im 90-Grad-Winkel drehen
page.Rotate = Rotation.on90;
// Informationen zur Seitenhöhe und -breite abrufen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Abmessungen einer Seite in einer PDF-Datei ermittelt. Wenn Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach Seitenabmessungen extrahieren und andere PDF-Manipulationsvorgänge durchführen. Aspose.PDF für .NET bietet große Flexibilität für die Arbeit mit PDF-Dateien und ermöglicht Ihnen die Entwicklung leistungsstarker und maßgeschneiderter Lösungen.

Erkunden Sie gerne die Dokumentation von Aspose.PDF weiter, um alle Funktionen dieser Bibliothek zu entdecken.
