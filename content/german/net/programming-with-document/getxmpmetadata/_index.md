---
title: XMP-Metadaten abrufen
linktitle: XMP-Metadaten abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit der GetXmpMetadata-Funktion von Aspose.PDF für .NET XMP-Metadaten mithilfe von C#-Quellcode aus einem PDF-Dokument extrahieren.
type: docs
weight: 200
url: /de/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF für .NET ist eine beliebte PDF-Manipulationsbibliothek, mit der Entwickler PDF-Dateien in ihren .NET-Anwendungen erstellen, bearbeiten und konvertieren können. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, XMP-Metadaten aus einem PDF-Dokument zu extrahieren. Dieses Tutorial führt Sie durch die Schritte zur Verwendung der`GetXmpMetadata` Funktion von Aspose.PDF für .NET zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen zu verwenden, müssen Sie zuerst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von der[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

 Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung der`GetXmpMetadata` Funktion zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, aus dem Sie XMP-Metadaten extrahieren möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, das Sie dann zum Extrahieren von XMP-Metadaten verwenden können.

## Schritt 3: XMP-Metadaten extrahieren

Um XMP-Metadaten aus einem PDF-Dokument zu extrahieren, können Sie den folgenden Code verwenden:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Im obigen Code`xmp:CreateDate`, `xmp:Nickname` , Und`xmp:CustomProperty` sind Beispiele für XMP-Metadateneigenschaften, die Sie aus einem PDF-Dokument extrahieren können. Sie können diese Eigenschaftsnamen durch die Namen beliebiger anderer XMP-Metadateneigenschaften ersetzen, die Sie extrahieren möchten.

### Beispiel-Quellcode zum Abrufen von XMP-Metadaten mit Aspose.PDF für .NET

 Hier ist der vollständige Quellcode zum Extrahieren von XMP-Metadaten aus einem PDF-Dokument mithilfe des`GetXmpMetadata` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extrahieren von XMP-Metadaten
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code extrahiert XMP-Metadaten aus dem PDF-Dokument und gibt sie an die Konsole aus.

## Abschluss

In diesem Tutorial haben wir besprochen, wie man mit Aspose.PDF für .NET XMP-Metadaten aus einem PDF-Dokument extrahiert. XMP-Metadaten liefern wertvolle Informationen zu einem Dokument, und Aspose.PDF für .NET ermöglicht Entwicklern, auf diese Informationen zuzugreifen und sie bei Bedarf in ihren Anwendungen zu verwenden. Durch das Extrahieren von XMP-Metadaten können Entwickler Einblicke in das Erstellungsdatum, den Autor und andere beschreibende Daten eines Dokuments gewinnen. Diese Informationen können verwendet werden, um die Funktionalität und das Benutzererlebnis von PDF-Anwendungen zu verbessern. Aspose.PDF für .NET bietet eine einfache und unkomplizierte API für den Zugriff auf XMP-Metadaten, wodurch sich diese Funktion problemlos in .NET-Anwendungen integrieren lässt.

### Häufig gestellte Fragen

#### F: Was sind XMP-Metadaten in einem PDF-Dokument?

A: XMP-Metadaten in einem PDF-Dokument beziehen sich auf Extensible Metadata Platform (XMP)-Informationen, die im Dokument eingebettet sind. XMP-Metadaten bieten eine Standardmethode zum Speichern von Informationen über das Dokument, wie Autor, Erstellungsdatum, Schlüsselwörter und andere beschreibende Daten. Sie ermöglichen das einfache Abrufen und Austauschen von Metadaten zwischen verschiedenen Systemen und Anwendungen.

#### F: Welche Art von Informationen können mit der Funktion „GetXmpMetadata“ extrahiert werden?

 A: Mit der Funktion GetXmpMetadata können Entwickler verschiedene XMP-Metadateneigenschaften aus einem PDF-Dokument extrahieren. Einige Beispiele für XMP-Metadateneigenschaften, die extrahiert werden können, sind`xmp:CreateDate`, `xmp:Nickname` , Und`xmp:CustomProperty`Entwickler können auf diese Eigenschaften zugreifen und sie nach Bedarf in ihren Anwendungen verwenden.

#### F: Kann ich mit Aspose.PDF für .NET benutzerdefinierte XMP-Metadateneigenschaften extrahieren?

A: Ja, Sie können benutzerdefinierte XMP-Metadateneigenschaften mit Aspose.PDF für .NET extrahieren. Benutzerdefinierte XMP-Metadateneigenschaften können in ein PDF-Dokument aufgenommen werden, um zusätzliche Informationen zu speichern, die für Ihre Anwendung oder Anforderungen spezifisch sind. Sie können diese benutzerdefinierten Eigenschaften nach Bedarf extrahieren und verwenden.

#### F: Kann Aspose.PDF für .NET andere Metadateninformationen aus einem PDF-Dokument extrahieren?

A: Ja, Aspose.PDF für .NET bietet verschiedene Funktionen zum Extrahieren von Metadateninformationen aus einem PDF-Dokument. Neben XMP-Metadaten können Sie auch Informationen wie Dokumentinformationen (Titel, Autor, Betreff, Schlüsselwörter), PDF-Version, Verschlüsselungsdetails und mehr extrahieren.