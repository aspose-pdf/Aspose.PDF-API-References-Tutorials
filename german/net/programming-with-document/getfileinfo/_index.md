---
title: Dateiinformationen abrufen
linktitle: Dateiinformationen abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die GetFileInfo-Funktion von Aspose.PDF für .NET verwenden, um Metadateninformationen zu einem PDF-Dokument abzurufen.
type: docs
weight: 180
url: /de/net/programming-with-document/getfileinfo/
---

 Aspose.PDF für .NET ist eine beliebte PDF-Bearbeitungsbibliothek, die es Entwicklern ermöglicht, PDF-Dateien in ihren .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, Informationen über die Metadaten eines PDF-Dokuments abzurufen. Dieses Tutorial führt Sie durch die Schritte zur Verwendung des`GetFileInfo`Funktion von Aspose.PDF für .NET zum Abrufen von Informationen über die Metadaten eines PDF-Dokuments.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen verwenden zu können, müssen Sie zunächst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

 Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung beginnen`GetFileInfo` Funktion zum Abrufen von Informationen über die Metadaten eines PDF-Dokuments.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, zu dem Sie Informationen abrufen möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, mit dem Sie dann Informationen über die Metadaten des Dokuments abrufen können.

## Schritt 3: Rufen Sie die Metadaten des Dokuments ab

Um Informationen zu den Metadaten eines PDF-Dokuments abzurufen, können Sie den folgenden Code verwenden:

```csharp
// Erhalten Sie Dokumentinformationen
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentinformationen anzeigen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Im obigen Code ruft jede Zeile eine andere Metadateneigenschaft des PDF-Dokuments ab und gibt sie an die Konsole aus. Sie können diesen Code anpassen, um nur die Eigenschaften abzurufen, an denen Sie interessiert sind.

### Beispielquellcode zum Abrufen von PDF-Dateiinformationen mit Aspose.PDF für .NET

 Hier ist der vollständige Quellcode zum Abrufen der Metadaten eines PDF-Dokuments mithilfe von`GetFileInfo` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Erhalten Sie Dokumentinformationen
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentinformationen anzeigen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```