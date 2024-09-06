---
title: Dateiinformationen in PDF-Datei abrufen
linktitle: Dateiinformationen in PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die GetFileInfo-Funktion in der PDF-Datei von Aspose.PDF für .NET verwenden, um Metadateninformationen zu einem PDF-Dokument abzurufen.
type: docs
weight: 180
url: /de/net/programming-with-document/getfileinfo/
---
 Aspose.PDF für .NET ist eine beliebte PDF-Manipulationsbibliothek, mit der Entwickler PDF-Dateien in ihren .NET-Anwendungen erstellen, bearbeiten und konvertieren können. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, Informationen über die Metadaten eines PDF-Dokuments abzurufen. Dieses Tutorial führt Sie durch die Schritte zur Verwendung der`GetFileInfo` Funktion von Aspose.PDF für .NET zum Abrufen von Informationen zu den Metadaten eines PDF-Dokuments.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen zu verwenden, müssen Sie zuerst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von der[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

 Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung der`GetFileInfo` Funktion zum Abrufen von Informationen zu den Metadaten eines PDF-Dokuments.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, zu dem Sie Informationen abrufen möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, mit dem Sie dann Informationen zu den Metadaten des Dokuments abrufen können.

## Schritt 3: Metadaten des Dokuments abrufen

Um Informationen zu den Metadaten eines PDF-Dokuments abzurufen, können Sie den folgenden Code verwenden:

```csharp
// Dokumentinformationen abrufen
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentinformationen anzeigen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Im obigen Code ruft jede Zeile eine andere Metadateneigenschaft des PDF-Dokuments ab und gibt sie an die Konsole aus. Sie können diesen Code anpassen, um nur die Eigenschaften abzurufen, die Sie interessieren.

### Beispielquellcode zum Abrufen von PDF-Dateiinformationen mit Aspose.PDF für .NET

 Hier ist der vollständige Quellcode zum Abrufen der Metadaten eines PDF-Dokuments mithilfe der`GetFileInfo` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Dokumentinformationen abrufen
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentinformationen anzeigen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Abschluss

In diesem Tutorial haben wir besprochen, wie Sie mit Aspose.PDF für .NET Informationen zu den Metadaten eines PDF-Dokuments abrufen können. Indem Sie ein PDF-Dokument laden und auf seine Metadateneigenschaften zugreifen, können Sie Informationen zu den Merkmalen und Eigenschaften des Dokuments sammeln. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API zum Arbeiten mit PDF-Dokumenten, einschließlich des Abrufens von Metadateninformationen, und ist damit ein wertvolles Tool für die PDF-Bearbeitung in .NET-Anwendungen.

### Häufig gestellte Fragen

#### F: Was sind Metadaten in einem PDF-Dokument?

A: Metadaten in einem PDF-Dokument beziehen sich auf Informationen, die die Eigenschaften und Merkmale des Dokuments beschreiben. Zu diesen Informationen gehören normalerweise Titel, Autor, Betreff, Schlüsselwörter, Erstellungsdatum, Änderungsdatum und mehr des Dokuments.

#### F: Wie kann ich Aspose.PDF für .NET in meinem .NET-Projekt installieren?

 A: Um Aspose.PDF für .NET zu installieren, müssen Sie die Bibliothek von der[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net). Extrahieren Sie nach dem Herunterladen den Inhalt der ZIP-Datei und fügen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzu.

#### F: Kann ich den Code anpassen, um nur bestimmte Metadateneigenschaften abzurufen?

A: Ja, Sie können den Code anpassen, um bestimmte Metadateneigenschaften abzurufen, indem Sie die Zeilen auskommentieren, die Sie nicht benötigen. Jede Zeile im Code entspricht einer bestimmten Metadateneigenschaft, sodass Sie Eigenschaften je nach Ihren Anforderungen ein- oder ausschließen können.

#### F: Welche Arten von Metadateneigenschaften kann ich mit Aspose.PDF für .NET abrufen?

A: Mit Aspose.PDF für .NET können Sie verschiedene Metadateneigenschaften eines PDF-Dokuments abrufen, darunter Autor, Titel, Betreff, Schlüsselwörter, Erstellungsdatum und Änderungsdatum.