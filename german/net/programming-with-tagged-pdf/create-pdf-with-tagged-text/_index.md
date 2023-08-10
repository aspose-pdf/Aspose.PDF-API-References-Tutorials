---
title: Erstellen Sie PDF mit getaggtem Text
linktitle: Erstellen Sie PDF mit getaggtem Text
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen einer PDF-Datei mit markiertem Text mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit getaggtem Text erstellen. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der Strukturfunktionen für markierte Inhalte von Aspose.PDF können Sie markierten Text zu Ihrem PDF-Dokument hinzufügen.

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

// Speichern Sie das PDF-Dokument
document.Save(dataDir + "PDFwithTagText.pdf");
```

Dieser Code erstellt ein leeres PDF-Dokument und fügt mit den von Aspose.PDF bereitgestellten Methoden markierten Text hinzu. Mit den entsprechenden Methoden können Sie weitere getaggte Textelemente wie Überschriften und Absätze hinzufügen.

### Beispielquellcode für „PDF mit markiertem Text erstellen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein PDF-Dokument
Document document = new Document();
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Legen Sie Titel und Sprache für Documentt fest
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Erstellen Sie Strukturelemente auf Textblockebene
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit getaggtem Text erstellen. Mit den markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie Ihren Text für eine bessere Zugänglichkeit und Semantik strukturieren und organisieren.

### FAQs

#### F: Was ist der Zweck der Erstellung eines PDF-Dokuments mit getaggtem Text mit Aspose.PDF für .NET?

A: Durch das Erstellen eines PDF-Dokuments mit getaggtem Text mit Aspose.PDF für .NET können Sie Ihren Textinhalt innerhalb des PDF-Dokuments strukturieren und organisieren. Mit Tags versehener Text fügt semantische Bedeutung hinzu und verbessert die Zugänglichkeit für Benutzer, insbesondere für diejenigen, die unterstützende Technologien verwenden.

#### F: Wie hilft Aspose.PDF beim Erstellen eines PDF-Dokuments mit getaggtem Text?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die mit Tags versehenen Inhaltsstrukturfunktionen der Bibliothek verwendet, um dem PDF-Dokument strukturierten und semantisch bedeutsamen Text hinzuzufügen.

#### F: Was sind die Voraussetzungen für die Erstellung eines PDF-Dokuments mit getaggtem Text mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Visual Studio mit dem .NET Framework installiert ist und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code ein PDF-Dokument mit getaggtem Text?

A: Das Codebeispiel zeigt, wie man ein PDF-Dokument erstellt, verschiedene getaggte Textelemente (z. B. Überschriften und Absätze) definiert und sie dem Inhalt des Dokuments hinzufügt. Dies wird mithilfe der von Aspose.PDF bereitgestellten Funktionen zur getaggten Inhaltsstruktur erreicht.

#### F: Wie kann ich die getaggten Textelemente wie Überschriften und Absätze anpassen?

 A: Sie können die getaggten Textelemente mithilfe geeigneter Methoden anpassen, z`CreateHeaderElement` Und`CreateParagraphElement` und das Festlegen von Eigenschaften wie`ActualText` um aussagekräftigen Text und Semantik bereitzustellen.

#### F: Kann ich mit ähnlichen Techniken andere getaggte Textelemente wie Listen oder Links hinzufügen?

A: Ja, Sie können mit ähnlichen Techniken andere getaggte Textelemente wie Listen, Links oder andere benutzerdefinierte Strukturen hinzufügen. Aspose.PDF bietet verschiedene Methoden zum Erstellen verschiedener Arten von getaggten Inhalten, sodass Sie die Dokumentsemantik verbessern können.

####  F: Wie funktioniert das?`SetTitle` method contribute to the PDF document's tagged text?

 A: Die`SetTitle` Die Methode legt den Titel des getaggten Inhalts des PDF-Dokuments fest und liefert eine kurze Beschreibung des Zwecks oder Themas des Dokuments. Diese Informationen helfen Benutzern, den Kontext des markierten Textes zu verstehen.

#### F: Wie verbessert die Verwendung von getaggtem Text die Barrierefreiheit in PDF-Dokumenten?

A: Mit Tags versehener Text verleiht dem Dokument eine semantische Bedeutung und macht es für Benutzer mit Behinderungen oder Menschen, die unterstützende Technologien verwenden, leichter zugänglich. Bildschirmlesegeräte und andere Hilfsgeräte können getaggten Text interpretieren und darstellen, um die Benutzererfahrung zu verbessern.

####  F: Wie funktioniert das?`SetLanguage` method enhance the tagged text in a PDF document?

 A: Die`SetLanguage`Die Methode legt das Sprachattribut des getaggten Inhalts des PDF-Dokuments fest. Dies hilft dabei, die Sprache anzugeben, in der der getaggte Text geschrieben ist, was die Zugänglichkeit verbessert und eine ordnungsgemäße sprachspezifische Wiedergabe ermöglicht.

#### F: Ist es mit ähnlichen Techniken möglich, neben getaggtem Text auch andere Elemente wie Bilder oder Multimedia hinzuzufügen?

A: Ja, Sie können mit ähnlichen Techniken neben getaggtem Text auch andere Elemente wie Bilder, Multimedia oder Anmerkungen hinzufügen. Aspose.PDF bietet zahlreiche Funktionen, um verschiedene Arten von Inhalten innerhalb des Dokuments zu kombinieren.