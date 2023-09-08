---
title: Holen Sie sich Dateiinformationen in einer PDF-Datei
linktitle: Holen Sie sich Dateiinformationen in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Funktion „GetFileInfo in PDF-Dateien“ von Aspose.PDF für .NET verwenden, um Metadateninformationen zu einem PDF-Dokument abzurufen.
type: docs
weight: 180
url: /de/net/programming-with-document/getfileinfo/
---
 Aspose.PDF für .NET ist eine beliebte PDF-Bearbeitungsbibliothek, die es Entwicklern ermöglicht, PDF-Dateien in ihren .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, Informationen über die Metadaten eines PDF-Dokuments abzurufen. Dieses Tutorial führt Sie durch die Schritte zur Verwendung des`GetFileInfo` Funktion von Aspose.PDF für .NET zum Abrufen von Informationen über die Metadaten eines PDF-Dokuments.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen verwenden zu können, müssen Sie zunächst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung beginnen`GetFileInfo` Funktion zum Abrufen von Informationen über die Metadaten eines PDF-Dokuments.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, zu dem Sie Informationen abrufen möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öffnen Sie das PDF-Dokument
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

//Öffnen Sie das PDF-Dokument
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

## Abschluss

In diesem Tutorial haben wir besprochen, wie Sie Aspose.PDF für .NET verwenden, um Informationen über die Metadaten eines PDF-Dokuments abzurufen. Durch das Laden eines PDF-Dokuments und den Zugriff auf seine Metadateneigenschaften können Sie Informationen über die Merkmale und Eigenschaften des Dokuments sammeln. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API für die Arbeit mit PDF-Dokumenten, einschließlich des Abrufens von Metadateninformationen, was es zu einem wertvollen Werkzeug für die PDF-Bearbeitung in .NET-Anwendungen macht.

### FAQs

#### F: Was sind Metadaten in einem PDF-Dokument?

A: Metadaten in einem PDF-Dokument beziehen sich auf die Informationen, die die Eigenschaften und Merkmale des Dokuments beschreiben. Zu diesen Informationen gehören in der Regel der Titel des Dokuments, der Autor, das Thema, Schlüsselwörter, das Erstellungsdatum, das Änderungsdatum und mehr.

#### F: Wie kann ich Aspose.PDF für .NET in meinem .NET-Projekt installieren?

 A: Um Aspose.PDF für .NET zu installieren, müssen Sie die Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net). Extrahieren Sie nach dem Herunterladen den Inhalt der ZIP-Datei und fügen Sie einen Verweis auf die Aspose.PDF für .NET-DLL in Ihrem .NET-Projekt hinzu.

#### F: Kann ich den Code anpassen, um nur bestimmte Metadateneigenschaften abzurufen?

A: Ja, Sie können den Code anpassen, um bestimmte Metadateneigenschaften abzurufen, indem Sie die Zeilen auskommentieren, die Sie nicht benötigen. Jede Zeile im Code entspricht einer bestimmten Metadateneigenschaft, sodass Sie Eigenschaften entsprechend Ihren Anforderungen einschließen oder ausschließen können.

#### F: Welche Arten von Metadateneigenschaften kann ich mit Aspose.PDF für .NET abrufen?

A: Mit Aspose.PDF für .NET können Sie verschiedene Metadateneigenschaften eines PDF-Dokuments abrufen, darunter Autor, Titel, Betreff, Schlüsselwörter, Erstellungsdatum und Änderungsdatum.