---
title: Holen Sie sich PDF-Seitenabmessungen
linktitle: Holen Sie sich PDF-Seitenabmessungen
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
 Wenn Sie die Seite drehen möchten, können Sie die verwenden`Rotate` Eigentum der`Page`Objekt. In diesem Beispiel wird die Seite um 90 Grad gedreht.

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

### FAQs zum Abrufen von PDF-Seitenabmessungen

#### F: Wie kann ich die Abmessungen einer bestimmten Seite in einer PDF-Datei ermitteln?

A: Um die Abmessungen einer bestimmten Seite in einer PDF-Datei zu erhalten, können Sie die verwenden`GetPageRect()` Methode der`Page` Objekt in Aspose.PDF für .NET. Diese Methode gibt a zurück`Rectangle` Objekt, das die Abmessungen (Breite und Höhe) der Seite enthält.

####  F: Was bedeutet das?`GetPageRect(true)` method do in the provided C# source code?

 A: Die`GetPageRect(true)` Die Methode im bereitgestellten C#-Quellcode gibt die Abmessungen der Seite nach Anwendung etwaiger Drehungen zurück. Wenn die Seite gedreht wird, gibt die Methode die Abmessungen der gedrehten Seite zurück, die von den ursprünglichen Abmessungen abweichen können.

#### F: Kann ich mit Aspose.PDF für .NET die Abmessungen aller Seiten im PDF-Dokument abrufen?

 A: Ja, Sie können die Abmessungen aller Seiten im PDF-Dokument ermitteln, indem Sie die durchlaufen`Pages` Sammlung der`Document` Objekt und Verwendung der`GetPageRect(true)` Methode für jede Seite.

#### F: Wie kann ich die Ausrichtung einer Seite (Hoch- oder Querformat) anhand ihrer Abmessungen bestimmen?

A: Um die Ausrichtung einer Seite anhand ihrer Abmessungen zu bestimmen, können Sie die Breite und Höhe der Seite vergleichen. Wenn die Breite größer als die Höhe ist, befindet sich die Seite im Querformat. Wenn die Höhe größer als die Breite ist, befindet sich die Seite im Hochformat.

#### F: Kann ich die Abmessungen einer Seite mit Aspose.PDF für .NET ändern?

 A: Ja, Sie können die Abmessungen einer Seite in Aspose.PDF für .NET ändern. Nach Erhalt der`Rectangle` Wenn Sie ein Objekt haben, das die Seitenabmessungen darstellt, können Sie die Breite und Höhe entsprechend Ihren Anforderungen anpassen und die Änderungen dann auf die Seite anwenden.