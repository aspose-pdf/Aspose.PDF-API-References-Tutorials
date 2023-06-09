---
title: PDF mit markiertem Bild erstellen
linktitle: PDF mit markiertem Bild erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen von PDFs mit getaggten Bildern mit Aspose.PDF für .NET.
type: docs
weight: 40
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellen. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der Strukturfunktionen für markierte Inhalte von Aspose.PDF können Sie markierte Bilder zu Ihrem PDF-Dokument hinzufügen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Sie können die Bibliothek von der offiziellen Website von Aspose herunterladen und auf Ihrem Computer installieren.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die Namespaces, die für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden erforderlich sind:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Schritt 3: Erstellen des PDF-Dokuments mit einem getaggten Bild

Verwenden Sie den folgenden Code, um ein PDF-Dokument mit einem getaggten Bild zu erstellen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Dieser Code erstellt ein leeres PDF-Dokument und fügt mithilfe der von Aspose.PDF bereitgestellten Methoden ein getaggtes Bild hinzu. Das Bild wird mit Alternativtext, Titel und Tag angegeben.

## Schritt 4: Speichern des PDF-Dokuments

Verwenden Sie den folgenden Code, um das PDF-Dokument zu speichern:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Dieser Code speichert das PDF-Dokument mit dem getaggten Bild in einer angegebenen Datei.

### Beispielquellcode für „PDF mit markiertem Bild erstellen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Bild mit einer Auflösung von 300 DPI hinzufügen (standardmäßig)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF-Dokument speichern
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellen. Mit Tags versehene Bilder fügen Ihrem PDF-Dokument zusätzliche, strukturierte Informationen hinzu.
