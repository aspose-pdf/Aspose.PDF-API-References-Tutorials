---
title: Holen Sie sich XMP-Metadaten
linktitle: Holen Sie sich XMP-Metadaten
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die GetXmpMetadata-Funktion von Aspose.PDF für .NET verwenden, um XMP-Metadaten aus einem PDF-Dokument mithilfe von C#-Quellcode zu extrahieren.
type: docs
weight: 200
url: /de/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF für .NET ist eine beliebte PDF-Bearbeitungsbibliothek, die es Entwicklern ermöglicht, PDF-Dateien in ihren .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, XMP-Metadaten aus einem PDF-Dokument zu extrahieren. Dieses Tutorial führt Sie durch die Schritte zur Verwendung des`GetXmpMetadata` Funktion von Aspose.PDF für .NET zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen verwenden zu können, müssen Sie zunächst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

 Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung beginnen`GetXmpMetadata` Funktion zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, aus dem Sie XMP-Metadaten extrahieren möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, das Sie dann zum Extrahieren von XMP-Metadaten verwenden können.

## Schritt 3: XMP-Metadaten extrahieren

Um XMP-Metadaten aus einem PDF-Dokument zu extrahieren, können Sie den folgenden Code verwenden:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Im obigen Code,`xmp:CreateDate`, `xmp:Nickname` , Und`xmp:CustomProperty`sind Beispiele für XMP-Metadateneigenschaften, die Sie aus einem PDF-Dokument extrahieren können. Sie können diese Eigenschaftsnamen durch die Namen aller anderen XMP-Metadateneigenschaften ersetzen, die Sie extrahieren möchten.

### Beispielquellcode zum Abrufen von XMP-Metadaten mit Aspose.PDF für .NET

 Hier ist der vollständige Quellcode zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument mithilfe von`GetXmpMetadata` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// XMP-Metadaten extrahieren
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code extrahiert XMP-Metadaten aus dem PDF-Dokument und gibt sie an die Konsole aus.