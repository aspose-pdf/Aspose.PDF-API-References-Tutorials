---
title: Alle Anmerkungen von der Seite abrufen
linktitle: Alle Anmerkungen von der Seite abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET alle Anmerkungen von einer PDF-Seite abrufen.
type: docs
weight: 70
url: /de/net/annotations/getallannotationsfrompage/
---
Dieser Artikel führt Sie durch den Prozess des Extrahierens aller Anmerkungen aus einer PDF-Seite mit Aspose.PDF für .NET. Aspose.PDF für .NET ist eine Bibliothek, mit der Entwickler PDF-Dokumente erstellen, bearbeiten und konvertieren können. Mithilfe dieses Handbuchs können Sie mithilfe des bereitgestellten C#-Quellcodes alle Anmerkungen einer bestimmten PDF-Seite abrufen.

Befolgen Sie die folgenden Schritte, um alle Anmerkungen für eine PDF-Seite mit Aspose.PDF für .NET abzurufen:

## Schritt 1: Der Pfad zum Dokumentenverzeichnis

Der erste Schritt beim Abrufen aller Anmerkungen von einer PDF-Seite mit Aspose.PDF für .NET besteht darin, den Pfad zum Dokumentenverzeichnis festzulegen, in dem Ihre PDF-Dateien gespeichert sind. Sie können dies tun, indem Sie die folgende Codezeile ändern:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Schritt 2: Ihre PDF-Dateien werden gespeichert

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den Pfad zu dem Ordner, in dem Ihre PDF-Dateien gespeichert sind. Zum Beispiel:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Schritt 3: Dokument öffnen

Der nächste Schritt besteht darin, das PDF-Dokument zu öffnen, das die Anmerkungen enthält, die Sie extrahieren möchten. Sie können dies tun, indem Sie den folgenden Code hinzufügen:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Diese Codezeile initialisiert eine neue Instanz der Document-Klasse und lädt das PDF-Dokument „GetAllAnnotationsFromPage.pdf“. Ersetzen Sie diesen Dateinamen durch den Namen Ihrer PDF-Datei.

## Schritt 4: Durchlaufen Sie alle Anmerkungen

Sobald Sie das PDF-Dokument geöffnet haben, können Sie alle Anmerkungen auf einer bestimmten Seite durchlaufen. Um beispielsweise alle Anmerkungen auf der ersten Seite des PDF-Dokuments zu durchlaufen, fügen Sie den folgenden Code hinzu:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Code kommt hierher
}
```

Dieser Code durchläuft alle Anmerkungen auf der ersten Seite des PDF-Dokuments und weist jede Anmerkung der Variablen „annotation“ zu.

## Schritt 5: Anmerkungseigenschaften abrufen

Um die Eigenschaften jeder Anmerkung zu extrahieren, können Sie den folgenden Code in die foreach-Schleife einfügen:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Dieser Code schreibt den Titel, den Betreff und den Inhalt jeder Anmerkung in die Konsole.

### Beispielquellcode für „Alle Anmerkungen von der Seite abrufen“ mit Aspose.PDF für .NET

Hier ist der vollständige Quellcode zum Abrufen aller Anmerkungen von einer PDF-Seite mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Gehen Sie alle Anmerkungen durch
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Anmerkungseigenschaften abrufen
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```
