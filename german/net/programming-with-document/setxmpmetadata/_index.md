---
title: Legen Sie XMPMetadata fest
linktitle: Legen Sie XMPMetadata fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET XMPMetadaten in PDF-Dateien festlegen. Befolgen Sie diese Schritt-für-Schritt-Anleitung.
type: docs
weight: 330
url: /de/net/programming-with-document/setxmpmetadata/
---
In diesem Artikel stellen wir eine Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für .NET zum Festlegen von XMP-Metadaten in einer PDF-Datei bereit. Am Ende des Artikels stellen wir einen vollständigen Beispielquellcode zur Verfügung.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

Bevor wir beginnen, müssen wir den Pfad zu dem Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir werden diesen Pfad in einer Variablen namens „dataDir“ speichern.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Unbedingt austauschen`YOUR DOCUMENT DIRECTORY` mit dem tatsächlichen Pfad zu Ihrer PDF-Datei.

## Schritt 2: Öffnen Sie die PDF-Datei

 Der erste Schritt besteht darin, die PDF-Datei zu öffnen, für die Sie XMP-Metadaten festlegen möchten. Dazu müssen Sie ein neues erstellen`Document` Objekt und übergeben Sie den Pfad zu Ihrer PDF-Datei.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Schritt 3: Legen Sie die XMP-Metadateneigenschaften fest

Nachdem Sie Ihre PDF-Datei geöffnet haben, können Sie mit dem Festlegen der XMP-Metadateneigenschaften beginnen. Welche Eigenschaften Sie festlegen, hängt von Ihren spezifischen Anforderungen ab, aber hier sind einige allgemeine Eigenschaften, die Sie möglicherweise festlegen möchten:

- `xmp:CreateDate`: Das Erstellungsdatum der PDF-Datei.
- `xmp:Nickname`: Ein Spitzname oder Alias für die PDF-Datei.
- `xmp:CustomProperty`: Eine benutzerdefinierte Eigenschaft mit einem von Ihnen angegebenen Wert.

 Um diese Eigenschaften festzulegen, können Sie die verwenden`Metadata` Eigentum der`Document` Objekt. Hier ist ein Beispiel:

```csharp
// Eigenschaften festlegen
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

In diesem Tutorial setzen wir das Erstellungsdatum auf das aktuelle Datum und die aktuelle Uhrzeit, den Spitznamen auf „Spitzname“ und eine benutzerdefinierte Eigenschaft auf „Benutzerdefinierter Wert“. Sie können diese Werte durch Ihre eigenen ersetzen.

## Schritt 4: Speichern Sie die PDF-Datei

 Nachdem Sie die XMP-Metadateneigenschaften festgelegt haben, müssen Sie die PDF-Datei speichern. Dazu können Sie die verwenden`Save` Methode der`Document` Objekt und übergeben Sie den Pfad zu dem Ort, an dem Sie die aktualisierte PDF-Datei speichern möchten.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Dokument speichern
pdfDocument.Save(dataDir);
```

### Beispielquellcode für Set XMPMetadata mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Festlegen von XMPMetadata mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Eigenschaften festlegen
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Dokument speichern
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```
