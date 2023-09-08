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

### FAQs

#### F: Was ist der Zweck der Erstellung eines PDF-Dokuments mit einem getaggten Bild mit Aspose.PDF für .NET?

A: Wenn Sie mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellen, können Sie dem Inhalt des Dokuments getaggte Bilder hinzufügen. Mit Tags versehene Bilder bieten strukturierte Informationen wie Alternativtext und Titel und verbessern so die Zugänglichkeit und Organisation.

#### F: Wie unterstützt die Aspose.PDF-Bibliothek die Erstellung eines PDF-Dokuments mit einem getaggten Bild?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die Strukturfunktionen der Bibliothek für getaggte Inhalte verwendet, um dem PDF-Dokument ein getaggtes Bild hinzuzufügen.

#### F: Was sind die Voraussetzungen für die Erstellung eines PDF-Dokuments mit einem getaggten Bild mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Visual Studio mit dem .NET Framework installiert ist und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code ein PDF-Dokument mit einem getaggten Bild?

A: Der Code zeigt, wie man ein PDF-Dokument erstellt, ein getaggtes Bildelement definiert und es dem Inhalt des Dokuments hinzufügt. Das getaggte Bild enthält mithilfe der von Aspose.PDF bereitgestellten Methoden Alternativtext, einen Titel und ein Tag.

#### F: Kann ich für das getaggte Bild unterschiedliche Bildformate verwenden?

A: Ja, Sie können für das getaggte Bild verschiedene Bildformate verwenden, z. B. JPEG, PNG, GIF usw. Das im Tutorial bereitgestellte Codebeispiel verwendet ein JPEG-Bild, Sie können es jedoch durch den Pfad zu einer Bilddatei in ersetzen Ihr bevorzugtes Format.

#### F: Wie wird der alternative Text (Alt-Text) in getaggten Bildern verwendet?

 A: Alt-Text bietet eine Textbeschreibung des Bildes, die von Bildschirmleseprogrammen für sehbehinderte Benutzer vorgelesen wird. Im bereitgestellten Code wird der Alternativtext mithilfe von festgelegt`AlternativeText` Eigentum der`IllustrationElement` Stellt das getaggte Bild dar.

####  F: Wie funktioniert das?`SetTitle` method contribute to the PDF document's tagged image?

 A: Die`SetTitle` Die Methode legt den Titel des getaggten Inhalts des PDF-Dokuments fest und stellt so zusätzlichen Kontext für das getaggte Bild bereit. Dieser Titel kann dabei helfen, den Zweck oder das Thema des getaggten Inhalts zu identifizieren.

#### F: Kann ich das Tag und den Titel des getaggten Bildes anpassen?

 A: Ja, Sie können das Tag und den Titel des getaggten Bildes mithilfe von anpassen`SetTag` Und`Title` Methoden der`IllustrationElement`. Das Codebeispiel zeigt, wie man das Tag auf „Abb“ und den Titel auf „Bild 1“ setzt.

#### F: Wie kann ich sicherstellen, dass das getaggte Bild zugänglich ist und den Barrierefreiheitsstandards entspricht?

A: Indem Sie die Strukturfunktionen für getaggte Inhalte von Aspose.PDF verwenden und Alternativtext und andere relevante Informationen bereitstellen, tragen Sie zur Zugänglichkeit des getaggten Bildes bei. Um die Einhaltung der Barrierefreiheitsstandards sicherzustellen, müssen Best Practices für Alternativtext und Dokumentstruktur befolgt werden.

#### F: Ist es möglich, mit ähnlichen Techniken mehrere getaggte Bilder zum selben PDF-Dokument hinzuzufügen?

 A: Ja, Sie können mit ähnlichen Techniken mehrere getaggte Bilder zum selben PDF-Dokument hinzufügen. Sie würden zusätzliche erstellen`IllustrationElement` Erstellen Sie Instanzen für jedes getaggte Bild und passen Sie deren Eigenschaften nach Bedarf an.