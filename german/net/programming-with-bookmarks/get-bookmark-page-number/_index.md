---
title: Lesezeichen-Seitenzahl in PDF-Datei abrufen
linktitle: Lesezeichen-Seitenzahl in PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach die Seitenzahl eines Lesezeichens in einer PDF-Datei speichern.
type: docs
weight: 60
url: /de/net/programming-with-bookmarks/get-bookmark-page-number/
---
Das Abrufen von Seitenzahlen, die Lesezeichen in einer PDF-Datei zugeordnet sind, kann für die Navigation hilfreich sein. Mit Aspose.PDF für .NET können Sie die Seitenzahl von Lesezeichen ganz einfach ermitteln, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf.Facades;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie die Lesezeichen-Seitenzahlen extrahieren möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

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

### FAQs zum Abrufen der Seitenzahl eines Lesezeichens in einer PDF-Datei

#### F: Was sind Lesezeichen in einer PDF-Datei?

A: Lesezeichen in einer PDF-Datei sind Navigationshilfen, die es Benutzern ermöglichen, schnell zu bestimmten Abschnitten oder Seiten innerhalb des Dokuments zu springen. Sie verbessern das Benutzererlebnis, indem sie Verknüpfungen zu relevanten Inhalten bereitstellen.

#### F: Warum sollte ich Lesezeichen-Seitenzahlen aus einer PDF-Datei abrufen?

A: Durch das Abrufen von Lesezeichenseitenzahlen können Benutzer effektiver durch ein Dokument navigieren und erhalten einen klaren Hinweis darauf, wohin jedes Lesezeichen führt. Dies ist besonders nützlich für längere Dokumente mit mehreren Abschnitten.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderliche Bibliothek für Ihr C#-Projekt zu importieren, verwenden Sie die folgende Importanweisung:

```csharp
using Aspose.Pdf.Facades;
```

Mit dieser Direktive können Sie die von Aspose.PDF für .NET bereitgestellten Klassen und Methoden verwenden.

#### F: Wie lege ich den Pfad zum Dokumentenordner fest?

 A: Ersetzen Sie im bereitgestellten Quellcode`"YOUR DOCUMENT DIRECTORY"`mit dem tatsächlichen Pfad zu dem Ordner, der die PDF-Datei enthält, aus der Sie Lesezeichen-Seitenzahlen extrahieren möchten. Dadurch wird sichergestellt, dass der Code die Ziel-PDF-Datei finden kann.

#### F: Wie erstelle ich einen Lesezeichen-Editor?

A: Um einen Lesezeichen-Editor zu erstellen, verwenden Sie den folgenden Code:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### F: Wie öffne ich eine PDF-Datei zur Lesezeichenbearbeitung?

A: Um eine PDF-Datei zum Extrahieren von Lesezeicheninformationen zu öffnen, verwenden Sie den folgenden Code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Ersetzen`"GetBookmarks.pdf"` mit dem tatsächlichen Dateinamen.

#### F: Wie extrahiere ich Lesezeichen aus der PDF-Datei?

 A: Um Lesezeichen aus der PDF-Datei zu extrahieren, verwenden Sie die`ExtractBookmarks` Methode des Lesezeichen-Editors:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### F: Wie kann ich die Seitenzahlen von Lesezeichen abrufen und anzeigen?

 A: Durchlaufen Sie die extrahierten Lesezeichen mit a`foreach` Schleife und Zugriff auf die`PageNumber` Eigenschaft jedes Lesezeichens, um die zugehörige Seitennummer abzurufen und anzuzeigen:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### F: Kann ich mit diesem Ansatz Lesezeicheneigenschaften ändern?

 A: Während sich dieses Tutorial auf das Abrufen von Lesezeichenseitenzahlen konzentriert, können Sie damit auch andere Lesezeicheneigenschaften ändern`Bookmark`Objekt und zugehörige Eigenschaften.

#### F: Wie speichere ich die aktualisierte PDF-Datei nach dem Extrahieren der Lesezeicheninformationen?

A: Durch die Lesezeichenextraktion wird die ursprüngliche PDF-Datei nicht verändert. Wenn Sie Änderungen speichern möchten, können Sie dies mit anderen von Aspose.PDF für .NET bereitgestellten Methoden tun.