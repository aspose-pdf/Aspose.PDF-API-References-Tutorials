---
title: Holen Sie sich Lesezeichen
linktitle: Holen Sie sich Lesezeichen
second_title: Aspose.PDF für .NET API-Referenz
description: Setzen Sie mit Aspose.PDF für .NET ganz einfach Lesezeichen für Ihre PDF-Dateien.
type: docs
weight: 70
url: /de/net/programming-with-bookmarks/get-bookmarks/
---

Das Abrufen von Lesezeichen aus einem PDF-Dokument kann für die Analyse der Struktur und der Navigationsinformationen des Dokuments nützlich sein. Mit Aspose.PDF für .NET können Sie die Lesezeichen ganz einfach abrufen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie die Lesezeichen extrahieren möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Jetzt öffnen wir das PDF-Dokument, aus dem wir die Lesezeichen extrahieren möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## Schritt 4: Lesezeichen durchsuchen

In diesem Schritt werden wir alle Lesezeichen im Dokument mit a durchlaufen`foreach` Schleife. Für jedes Lesezeichen zeigen wir Informationen wie Titel, Kursivschrift, Fettschrift und Farbe an. Hier ist der entsprechende Code:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Beispielquellcode für „Lesezeichen abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Gehen Sie alle Lesezeichen durch
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Erstellen von Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie Lesezeichen analysieren und Informationen zu jedem Lesezeichen in Ihren PDF-Dokumenten extrahieren.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.