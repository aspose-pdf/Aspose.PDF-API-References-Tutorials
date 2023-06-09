---
title: Links extrahieren
linktitle: Links extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie ganz einfach Links aus einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/programming-with-links-and-actions/extract-links/
---

Durch das Extrahieren von Links aus einem PDF-Dokument können Sie alle im Dokument vorhandenen Hypertext-Links wiederherstellen. Mit Aspose.PDF für .NET können Sie diese Links ganz einfach extrahieren, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie die Links extrahieren möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

 Wir öffnen das PDF-Dokument mit`Document` Klasse. Hier ist der entsprechende Code:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Schritt 4: Links extrahieren

 In diesem Schritt extrahieren wir die im PDF-Dokument vorhandenen Links mithilfe von`AnnotationSelector` Klasse. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode zum Extrahieren von Links mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Aktionen extrahieren
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Extrahieren von Links aus einem PDF-Dokument mit Aspose.PDF für .NET. Mit diesem Code können Sie alle im Dokument vorhandenen Hyperlinks abrufen.

Weitere Informationen zu erweiterten Funktionen zur Linkextraktion finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.