---
title: PDF mit markiertem Bild erstellen
linktitle: PDF mit markiertem Bild erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen von PDFs mit getaggten Bildern mit Aspose.PDF für .NET.
type: docs
weight: 40
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In diesem Tutorial geben wir Ihnen eine Schritt-für-Schritt-Anleitung zum Erstellen eines PDF-Dokuments mit einem getaggten Bild mithilfe von Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der getaggten Inhaltsstrukturfunktionen von Aspose.PDF können Sie getaggte Bilder zu Ihrem PDF-Dokument hinzufügen.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Sie können die Bibliothek von der offiziellen Aspose-Website herunterladen und auf Ihrem Computer installieren.

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

Dieser Code speichert das PDF-Dokument mit dem markierten Bild in einer angegebenen Datei.

### Beispielquellcode zum Erstellen von PDFs mit markierten Bildern unter Verwendung von Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellen. Markierte Bilder fügen Ihrem PDF-Dokument zusätzliche, strukturierte Informationen hinzu.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Erstellung eines PDF-Dokuments mit einem getaggten Bild mit Aspose.PDF für .NET?

A: Wenn Sie mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellen, können Sie getaggte Bilder zum Inhalt des Dokuments hinzufügen. Getaggte Bilder bieten strukturierte Informationen wie Alternativtext und Titel und verbessern so die Zugänglichkeit und Organisation.

#### F: Wie hilft die Aspose.PDF-Bibliothek beim Erstellen eines PDF-Dokuments mit einem getaggten Bild?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die getaggten Inhaltsstrukturfunktionen der Bibliothek verwendet, um dem PDF-Dokument ein getaggtes Bild hinzuzufügen.

#### F: Was sind die Voraussetzungen zum Erstellen eines PDF-Dokuments mit einem getaggten Bild mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Visual Studio mit dem .NET-Framework installiert haben und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code ein PDF-Dokument mit einem getaggten Bild?

A: Der Code zeigt, wie man ein PDF-Dokument erstellt, ein getaggtes Bildelement definiert und es dem Inhalt des Dokuments hinzufügt. Das getaggte Bild enthält Alternativtext, einen Titel und ein Tag mit Methoden, die von Aspose.PDF bereitgestellt werden.

#### F: Kann ich für das getaggte Bild verschiedene Bildformate verwenden?

A: Ja, Sie können für das markierte Bild verschiedene Bildformate verwenden, z. B. JPEG, PNG, GIF usw. Das im Tutorial bereitgestellte Codebeispiel verwendet ein JPEG-Bild, Sie können es jedoch durch den Pfad zu einer Bilddatei in Ihrem bevorzugten Format ersetzen.

#### F: Wie wird der alternative Text (Alt-Text) in getaggten Bildern verwendet?

 A: Alternativtext bietet eine Textbeschreibung des Bildes, die von Bildschirmleseprogrammen für sehbehinderte Benutzer vorgelesen wird. Im bereitgestellten Code wird der Alternativtext mithilfe des`AlternativeText` Eigentum der`IllustrationElement` stellt das markierte Bild dar.

####  F: Wie funktioniert das`SetTitle` method contribute to the PDF document's tagged image?

 A: Die`SetTitle` Die Methode legt den Titel des getaggten Inhalts des PDF-Dokuments fest und bietet zusätzlichen Kontext für das getaggte Bild. Dieser Titel kann dabei helfen, den Zweck oder das Thema des getaggten Inhalts zu identifizieren.

#### F: Kann ich das Tag und den Titel des getaggten Bildes anpassen?

 A: Ja, Sie können das Tag und den Titel des getaggten Bildes anpassen, indem Sie`SetTag` Und`Title` Methoden der`IllustrationElement`Das Codebeispiel zeigt, wie das Tag auf „Abb.“ und der Titel auf „Bild 1“ gesetzt wird.

#### F: Wie kann ich sicherstellen, dass das markierte Bild zugänglich ist und den Zugänglichkeitsstandards entspricht?

A: Indem Sie die getaggten Inhaltsstrukturfunktionen von Aspose.PDF verwenden und Alternativtext und andere relevante Informationen bereitstellen, tragen Sie zur Zugänglichkeit des getaggten Bildes bei. Um die Einhaltung der Zugänglichkeitsstandards sicherzustellen, müssen Sie Best Practices für Alternativtext und Dokumentstruktur befolgen.

#### F: Ist es möglich, mit ähnlichen Techniken mehrere markierte Bilder zum selben PDF-Dokument hinzuzufügen?

 A: Ja, Sie können mehrere getaggte Bilder mit ähnlichen Techniken zum selben PDF-Dokument hinzufügen. Sie erstellen zusätzliche`IllustrationElement` Instanzen für jedes markierte Bild und passen Sie deren Eigenschaften nach Bedarf an.