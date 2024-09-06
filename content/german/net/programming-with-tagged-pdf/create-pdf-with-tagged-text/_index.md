---
title: PDF mit getaggtem Text erstellen
linktitle: PDF mit getaggtem Text erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen einer PDF-Datei mit getaggtem Text mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
In diesem Tutorial geben wir Ihnen eine Schritt-für-Schritt-Anleitung zum Erstellen eines PDF-Dokuments mit getaggtem Text mithilfe von Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der getaggten Inhaltsstrukturfunktionen von Aspose.PDF können Sie getaggten Text zu Ihrem PDF-Dokument hinzufügen.

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

## Schritt 3: Erstellen des PDF-Dokuments mit getaggtem Text

Verwenden Sie den folgenden Code, um ein PDF-Dokument mit getaggtem Text zu erstellen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Fügen Sie hier weitere Absätze hinzu

// Speichern des PDF-Dokuments
document.Save(dataDir + "PDFwithTagText.pdf");
```

Dieser Code erstellt ein leeres PDF-Dokument und fügt getaggten Text mit den von Aspose.PDF bereitgestellten Methoden hinzu. Sie können mit den entsprechenden Methoden andere getaggte Textelemente wie Überschriften und Absätze hinzufügen.

### Beispielquellcode zum Erstellen von PDFs mit markiertem Text unter Verwendung von Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Dokument erstellen
Document document = new Document();
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Titel und Sprache für Dokument festlegen
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Erstellen von Strukturelementen auf Textblockebene
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// PDF-Dokument speichern
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit getaggtem Text erstellen. Mit den markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie Ihren Text strukturieren und organisieren, um die Zugänglichkeit und Semantik zu verbessern.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Erstellung eines PDF-Dokuments mit getaggtem Text mit Aspose.PDF für .NET?

A: Wenn Sie mit Aspose.PDF für .NET ein PDF-Dokument mit getaggtem Text erstellen, können Sie Ihren Textinhalt im PDF-Dokument strukturieren und organisieren. Getaggter Text fügt semantische Bedeutung hinzu und verbessert die Zugänglichkeit für Benutzer, insbesondere für diejenigen, die unterstützende Technologien verwenden.

#### F: Wie hilft Aspose.PDF beim Erstellen eines PDF-Dokuments mit getaggtem Text?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die getaggten Inhaltsstrukturfunktionen der Bibliothek verwendet, um dem PDF-Dokument strukturierten und semantisch sinnvollen Text hinzuzufügen.

#### F: Was sind die Voraussetzungen zum Erstellen eines PDF-Dokuments mit getaggtem Text mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Visual Studio mit dem .NET-Framework installiert haben und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code ein PDF-Dokument mit getaggtem Text?

A: Das Codebeispiel zeigt, wie Sie ein PDF-Dokument erstellen, verschiedene getaggte Textelemente (wie Überschriften und Absätze) definieren und sie dem Inhalt des Dokuments hinzufügen. Dies wird mithilfe der getaggten Inhaltsstrukturfunktionen von Aspose.PDF erreicht.

#### F: Wie kann ich die getaggten Textelemente wie Überschriften und Absätze anpassen?

 A: Sie können die getaggten Textelemente mithilfe geeigneter Methoden anpassen, wie zum Beispiel`CreateHeaderElement` Und`CreateParagraphElement` und das Festlegen von Eigenschaften wie`ActualText` um aussagekräftigen Text und Semantik bereitzustellen.

#### F: Kann ich mit ähnlichen Techniken andere getaggte Textelemente wie Listen oder Links hinzufügen?

A: Ja, Sie können mit ähnlichen Techniken andere getaggte Textelemente wie Listen, Links oder andere benutzerdefinierte Strukturen hinzufügen. Aspose.PDF bietet verschiedene Methoden zum Erstellen unterschiedlicher Arten getaggter Inhalte, sodass Sie die Dokumentsemantik verbessern können.

####  F: Wie funktioniert das`SetTitle` method contribute to the PDF document's tagged text?

 A: Die`SetTitle` Die Methode legt den Titel des getaggten Inhalts des PDF-Dokuments fest und bietet eine kurze Beschreibung des Zwecks oder Themas des Dokuments. Diese Informationen helfen Benutzern, den Kontext des getaggten Textes zu verstehen.

#### F: Wie verbessert die Verwendung von getaggtem Text die Zugänglichkeit in PDF-Dokumenten?

A: Markierter Text verleiht dem Dokument eine semantische Bedeutung und macht es für Benutzer mit Behinderungen oder Benutzer unterstützender Technologien leichter zugänglich. Bildschirmleseprogramme und andere unterstützende Geräte können markierten Text interpretieren und darstellen, um das Benutzererlebnis zu verbessern.

####  F: Wie funktioniert das`SetLanguage` method enhance the tagged text in a PDF document?

 A: Die`SetLanguage`Die Methode legt das Sprachattribut des getaggten Inhalts des PDF-Dokuments fest. Dies hilft dabei, die Sprache anzugeben, in der der getaggte Text geschrieben ist, was die Zugänglichkeit verbessert und eine korrekte sprachspezifische Darstellung ermöglicht.

#### F: Ist es möglich, mithilfe ähnlicher Techniken neben getaggtem Text andere Elemente wie Bilder oder Multimedia-Inhalte hinzuzufügen?

A: Ja, Sie können mit ähnlichen Techniken neben getaggtem Text andere Elemente wie Bilder, Multimedia oder Anmerkungen hinzufügen. Aspose.PDF bietet eine breite Palette von Funktionen zum Kombinieren verschiedener Inhaltstypen im Dokument.