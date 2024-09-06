---
title: XMPMetadata in PDF-Datei festlegen
linktitle: XMPMetadata in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET XMPMetadata in einer PDF-Datei festlegen. Folgen Sie dieser Schritt-für-Schritt-Anleitung.
type: docs
weight: 330
url: /de/net/programming-with-document/setxmpmetadata/
---
In diesem Artikel geben wir eine Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für .NET zum Festlegen von XMP-Metadaten in einer PDF-Datei. Am Ende des Artikels stellen wir einen vollständigen Beispielquellcode zur Verfügung.

## Schritt 1: Pfad zum Dokumentverzeichnis festlegen

Bevor wir beginnen, müssen wir den Pfad zum Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir speichern diesen Pfad in einer Variablen namens „dataDir“.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie unbedingt`YOUR DOCUMENT DIRECTORY` durch den tatsächlichen Pfad zu Ihrer PDF-Datei.

## Schritt 2: Öffnen Sie die PDF-Datei

 Der erste Schritt besteht darin, die PDF-Datei zu öffnen, für die Sie XMP-Metadaten festlegen möchten. Dazu müssen Sie eine neue`Document` Objekt und geben Sie den Pfad zu Ihrer PDF-Datei ein.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Schritt 3: XMP-Metadateneigenschaften festlegen

Nachdem Sie Ihre PDF-Datei geöffnet haben, können Sie mit dem Festlegen der XMP-Metadateneigenschaften beginnen. Die von Ihnen festgelegten Eigenschaften hängen von Ihren spezifischen Anforderungen ab. Hier sind jedoch einige allgemeine Eigenschaften, die Sie möglicherweise festlegen möchten:

- `xmp:CreateDate`: Das Erstellungsdatum der PDF-Datei.
- `xmp:Nickname`: Ein Spitzname oder Alias für die PDF-Datei.
- `xmp:CustomProperty`: Eine benutzerdefinierte Eigenschaft mit einem von Ihnen angegebenen Wert.

 Um diese Eigenschaften festzulegen, können Sie die`Metadata` Eigentum der`Document` Objekt. Hier ist ein Beispiel:

```csharp
// Festlegen von Eigenschaften
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

In diesem Tutorial setzen wir das Erstellungsdatum auf das aktuelle Datum und die aktuelle Uhrzeit, den Spitznamen auf „Spitzname“ und eine benutzerdefinierte Eigenschaft auf „Benutzerdefinierter Wert“. Sie können diese Werte durch Ihre eigenen ersetzen.

## Schritt 4: Speichern Sie die PDF-Datei

 Nachdem Sie die XMP-Metadateneigenschaften festgelegt haben, müssen Sie die PDF-Datei speichern. Dazu können Sie das`Save` Methode der`Document` Objekt und geben Sie den Pfad ein, unter dem Sie die aktualisierte PDF-Datei speichern möchten.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Dokument speichern
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Festlegen von XMPMetadata mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Festlegen von XMPMetadata mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Festlegen von Eigenschaften
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Dokument speichern
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## Abschluss

Aspose.PDF für .NET bietet eine unkomplizierte Möglichkeit, XMP-Metadaten in PDF-Dateien festzulegen, sodass Sie Ihren Dokumenten beschreibende Informationen und Eigenschaften hinzufügen können. Die oben bereitgestellte Schritt-für-Schritt-Anleitung zeigt Ihnen, wie Sie mithilfe von C#-Quellcode verschiedene XMP-Metadateneigenschaften festlegen. Darüber hinaus können Sie die XMP-Metadaten an Ihre spezifischen Anforderungen und Geschäftsanforderungen anpassen. Mit Aspose.PDF für .NET wird die Verwaltung von PDF-Metadaten effizienter und ermöglicht eine bessere Organisation und Durchsuchbarkeit Ihrer PDF-Dokumente.

### FAQs zum Festlegen von XMP-Metadaten in einer PDF-Datei

#### F: Was sind XMP-Metadaten in einer PDF-Datei und warum sind sie wichtig?

A: XMP (Extensible Metadata Platform) ist ein Standard zum Einbetten von Metadaten in verschiedene Dateiformate, einschließlich PDF. XMP-Metadaten in einer PDF-Datei ermöglichen es Ihnen, dem Dokument beschreibende Informationen und Eigenschaften hinzuzufügen, wie z. B. Erstellungsdatum, Autor, Titel, Schlüsselwörter und benutzerdefinierte Eigenschaften. Dies ist für eine bessere Organisation, Durchsuchbarkeit und Archivierung von PDF-Dokumenten unerlässlich.

#### F: Kann ich außer den im Beispiel genannten noch andere XMP-Metadateneigenschaften festlegen?

 A: Ja, Sie können je nach Ihren spezifischen Anforderungen eine Vielzahl von XMP-Metadateneigenschaften festlegen. Einige allgemeine Eigenschaften sind`dc:title` (Titel des Dokuments),`dc:creator` (Dokumentenersteller),`dc:description` (Dokumentbeschreibung),`pdf:Keywords` (Dokumentschlüsselwörter) und mehr. Die XMP-Spezifikation bietet verschiedene Standard-Namespaces und benutzerdefinierte Namespaces zum Festlegen verschiedener Arten von Metadaten.

#### F: Ist es möglich, XMP-Metadaten aus einer vorhandenen PDF-Datei abzurufen und zu lesen?

 A: Ja, Aspose.PDF für .NET bietet die Möglichkeit, XMP-Metadaten aus einer vorhandenen PDF-Datei zu lesen und abzurufen. Sie können den`Metadata` Eigentum der`Document` Klasse, um auf die XMP-Metadaten zuzugreifen und die Werte bestimmter Eigenschaften abzurufen.