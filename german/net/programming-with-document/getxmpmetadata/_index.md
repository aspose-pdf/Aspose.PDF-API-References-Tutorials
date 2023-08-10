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

//Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"`mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, das Sie dann zum Extrahieren von XMP-Metadaten verwenden können.

## Schritt 3: XMP-Metadaten extrahieren

Um XMP-Metadaten aus einem PDF-Dokument zu extrahieren, können Sie den folgenden Code verwenden:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Im obigen Code,`xmp:CreateDate`, `xmp:Nickname` , Und`xmp:CustomProperty` sind Beispiele für XMP-Metadateneigenschaften, die Sie aus einem PDF-Dokument extrahieren können. Sie können diese Eigenschaftsnamen durch die Namen aller anderen XMP-Metadateneigenschaften ersetzen, die Sie extrahieren möchten.

### Beispielquellcode zum Abrufen von XMP-Metadaten mit Aspose.PDF für .NET

 Hier ist der vollständige Quellcode zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument mithilfe von`GetXmpMetadata` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// XMP-Metadaten extrahieren
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code extrahiert XMP-Metadaten aus dem PDF-Dokument und gibt sie an die Konsole aus.

## Abschluss

In diesem Tutorial haben wir besprochen, wie Sie Aspose.PDF für .NET verwenden, um XMP-Metadaten aus einem PDF-Dokument zu extrahieren. XMP-Metadaten liefern wertvolle Informationen über ein Dokument und Aspose.PDF für .NET ermöglicht Entwicklern den Zugriff auf diese Informationen und deren Verwendung in ihren Anwendungen nach Bedarf. Durch das Extrahieren von XMP-Metadaten können Entwickler Einblicke in das Erstellungsdatum, den Autor und andere beschreibende Daten eines Dokuments gewinnen. Diese Informationen können verwendet werden, um die Funktionalität und Benutzererfahrung von PDF-Anwendungen zu verbessern. Aspose.PDF für .NET bietet eine einfache und unkomplizierte API für den Zugriff auf XMP-Metadaten und erleichtert so die Integration dieser Funktion in .NET-Anwendungen.

### FAQs

#### F: Was sind XMP-Metadaten in einem PDF-Dokument?

A: XMP-Metadaten in einem PDF-Dokument beziehen sich auf XMP-Informationen (Extensible Metadata Platform), die in das Dokument eingebettet sind. XMP-Metadaten bieten eine Standardmethode zum Speichern von Informationen über das Dokument, wie z. B. Autor, Erstellungsdatum, Schlüsselwörter und andere beschreibende Daten. Es ermöglicht den einfachen Abruf und Austausch von Metadaten über verschiedene Systeme und Anwendungen hinweg.

#### F: Welche Art von Informationen können mit der Funktion „GetXmpMetadata“ extrahiert werden?

 A: Mit der Funktion „GetXmpMetadata“ können Entwickler verschiedene XMP-Metadateneigenschaften aus einem PDF-Dokument extrahieren. Einige Beispiele für XMP-Metadateneigenschaften, die extrahiert werden können, sind:`xmp:CreateDate`, `xmp:Nickname` , Und`xmp:CustomProperty`. Entwickler können auf diese Eigenschaften zugreifen und sie nach Bedarf in ihren Anwendungen verwenden.

#### F: Kann ich benutzerdefinierte XMP-Metadateneigenschaften mit Aspose.PDF für .NET extrahieren?

A: Ja, Sie können benutzerdefinierte XMP-Metadateneigenschaften mit Aspose.PDF für .NET extrahieren. Benutzerdefinierte XMP-Metadateneigenschaften können in ein PDF-Dokument eingefügt werden, um zusätzliche Informationen speziell für Ihre Anwendung oder Anforderungen zu speichern. Sie können diese benutzerdefinierten Eigenschaften nach Bedarf extrahieren und verwenden.

#### F: Ist Aspose.PDF für .NET in der Lage, andere Metadateninformationen aus einem PDF-Dokument zu extrahieren?

A: Ja, Aspose.PDF für .NET bietet verschiedene Funktionen zum Extrahieren von Metadateninformationen aus einem PDF-Dokument. Neben XMP-Metadaten können Sie auch Informationen wie Dokumentinformationen (Titel, Autor, Betreff, Schlüsselwörter), PDF-Version, Verschlüsselungsdetails und mehr extrahieren.