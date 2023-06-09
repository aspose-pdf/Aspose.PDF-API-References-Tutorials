---
title: Holen Sie sich die Seitenzahl des Lesezeichens
linktitle: Holen Sie sich die Seitenzahl des Lesezeichens
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach Lesezeichen-Seitenzahlen aus Ihren PDF-Dateien erstellen.
type: docs
weight: 60
url: /de/net/programming-with-bookmarks/get-bookmark-page-number/
---

Das Abrufen von Seitenzahlen, die Lesezeichen in einem PDF-Dokument zugeordnet sind, kann für die Navigation hilfreich sein. Mit Aspose.PDF für .NET können Sie die Seitenzahl von Lesezeichen ganz einfach ermitteln, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf.Facades;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie die Lesezeichen-Seitenzahlen extrahieren möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Erstellen Sie den Lesezeichen-Editor

 Jetzt erstellen wir eine`PdfBookmarkEditor` Objekt, um die Lesezeichen des Dokuments zu manipulieren. Verwenden Sie den folgenden Code:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Schritt 4: Öffnen Sie die PDF-Datei

 In diesem Schritt öffnen wir die PDF-Datei mit`BindPdf` Methode des Lesezeichen-Editors. Hier ist der entsprechende Code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Schritt 5: Lesezeichen extrahieren

 Jetzt extrahieren wir die Lesezeichen mithilfe von aus dem Dokument`ExtractBookmarks` Methode des Lesezeichen-Editors. Hier ist der entsprechende Code:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Schritt 6: Lesezeichen durchsuchen und Seitenzahlen abrufen

 Schließlich durchlaufen wir die extrahierten Lesezeichen und ermitteln mithilfe von a die Seitenzahlen, die jedem Lesezeichen zugeordnet sind`foreach` Schleife. Hier ist der entsprechende Code:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Beispielquellcode für „Get Bookmark Page Number“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie einen PDFBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// PDF-Datei öffnen
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Lesezeichen extrahieren
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Abrufen von Lesezeichen-Seitenzahlen mit Aspose.PDF für .NET. Mit diesem Code können Sie die Navigationsinformationen abrufen, die jedem Lesezeichen in Ihren PDF-Dokumenten zugeordnet sind.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.