---
title: Holen Sie sich untergeordnete Lesezeichen
linktitle: Holen Sie sich untergeordnete Lesezeichen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET erhalten Sie ganz einfach untergeordnete Lesezeichen Ihrer PDF-Dateien.
type: docs
weight: 80
url: /de/net/programming-with-bookmarks/get-child-bookmarks/
---

Das Abrufen untergeordneter Lesezeichen aus einem PDF-Dokument kann hilfreich sein, um die hierarchische Struktur von Lesezeichen zu erkunden. Mit Aspose.PDF für .NET können Sie die untergeordneten Lesezeichen ganz einfach abrufen, indem Sie dem folgenden Quellcode folgen:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Schritt 4: Durchsuchen Sie Lesezeichen und untergeordnete Lesezeichen

In diesem Schritt werden wir alle Lesezeichen im Dokument mit a durchlaufen`foreach`Schleife. Für jedes Lesezeichen zeigen wir Informationen wie Titel, Kursivschrift, Fettschrift und Farbe an. Wenn das Lesezeichen untergeordnete Lesezeichen hat, werden diese ebenfalls angezeigt. Hier ist der entsprechende Code:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Durchsuchen Sie auch untergeordnete Lesezeichen
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Beispielquellcode für „Get Child Bookmarks“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Gehen Sie alle Lesezeichen durch
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Es gibt untergeordnete Lesezeichen, die dann auch durchlaufen werden
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Erstellen untergeordneter Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie die hierarchische Struktur von Lesezeichen erkunden und detaillierte Informationen zu jedem Lesezeichen und seinen untergeordneten Lesezeichen in Ihren PDF-Dokumenten erhalten.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.