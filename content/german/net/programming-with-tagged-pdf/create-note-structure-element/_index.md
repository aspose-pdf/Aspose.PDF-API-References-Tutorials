---
title: Notizstrukturelement erstellen
linktitle: Notizstrukturelement erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen strukturierter Notizelemente in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 30
url: /de/net/programming-with-tagged-pdf/create-note-structure-element/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, wie Sie mit Aspose.PDF für .NET ein Notizstrukturelement in einem PDF-Dokument erstellen. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie strukturierte Notizen zu Ihrem PDF-Dokument hinzufügen.

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

## Schritt 3: Erstellen des PDF-Dokuments und der strukturierten Notizelemente

Verwenden Sie den folgenden Code, um ein PDF-Dokument zu erstellen und Notizstrukturelemente hinzuzufügen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Dieser Code erstellt ein leeres PDF-Dokument und fügt einem Absatz strukturierte Notizelemente hinzu. Jede Notiz wird mit den von Aspose.PDF bereitgestellten Methoden erstellt.

## Schritt 4: Speichern des PDF-Dokuments

Verwenden Sie den folgenden Code, um das PDF-Dokument zu speichern:

```csharp
document. Save(outFile);
```

Dieser Code speichert das PDF-Dokument mit den Notizstrukturelementen in einer angegebenen Datei.

### Beispielquellcode zum Erstellen eines Notizstrukturelements mit Aspose.PDF für .NET 

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Erstellen Sie ein PDF-Dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Absatzelement hinzufügen
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement hinzufügen
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement hinzufügen
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement hinzufügen
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Muss eine Ausnahme auslösen – Aspose.Pdf.Tagged.TaggedException: Strukturelement mit ID='note_002' existiert bereits
//note3.SetId("note_002");
// Das resultierende Dokument entspricht nicht PDF/UA, wenn ClearId() für das Notizstrukturelement verwendet wird
//note3.ClearId();
// Markiertes PDF-Dokument speichern
document.Save(outFile);
// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Notizstrukturelemente in einem PDF-Dokument erstellen. Mit strukturierten Notizelementen können Sie Ihrem PDF-Dokument zusätzliche, strukturierte Informationen hinzufügen.

### FAQs

#### F: Was ist der Zweck der Erstellung von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Erstellen von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET können Sie strukturierte Notizen zum Inhalt des Dokuments hinzufügen. Diese Notizen können zusätzlichen Kontext, Erklärungen oder Verweise auf bestimmte Teile des Inhalts bereitstellen.

#### F: Wie unterstützt die Aspose.PDF-Bibliothek die Erstellung von Notizstrukturelementen in einem PDF-Dokument?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die markierten Inhaltsstrukturfunktionen der Bibliothek verwendet, um strukturierte Notizelemente innerhalb des Inhalts des PDF-Dokuments zu erstellen.

#### F: Was sind die Voraussetzungen für die Erstellung von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Visual Studio mit dem .NET Framework installiert ist und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code Notizstrukturelemente im Inhalt des PDF-Dokuments?

A: Der Code zeigt, wie man ein PDF-Dokument erstellt, strukturierte Notizelemente definiert und sie einem Absatz hinzufügt. Jede Notiz wird mit den von Aspose.PDF bereitgestellten Methoden erstellt, sodass Sie strukturierte Notizen in den Inhalt integrieren können.

#### F: Kann ich den Inhalt und die Eigenschaften der von mir erstellten Notizstrukturelemente anpassen?

A: Ja, Sie können den Inhalt und die Eigenschaften von Notizstrukturelementen anpassen, indem Sie die Methoden und Eigenschaften verwenden, die von der Aspose.PDF-Bibliothek bereitgestellt werden. Der Code zeigt, wie Sie den Text und die ID von Notizelementen festlegen. Sie können diese jedoch nach Bedarf weiter anpassen.

#### F: Wie wird die hierarchische Beziehung zwischen den Notizstrukturelementen und dem Inhalt des Dokuments hergestellt?

 A: Die hierarchische Beziehung wird durch das Hinzufügen von Notizstrukturelementen als untergeordnete Elemente anderer strukturierter Elemente, z. B. Absätze, hergestellt. Im Code werden Notizelemente mithilfe von an ein Absatzelement angehängt`AppendChild` Methode.

#### F: Kann ich Notizstrukturelementen eindeutige IDs zuweisen?

A: Ja, Sie können Notizstrukturelementen mithilfe von eindeutige IDs zuweisen`SetId` Methode. Der Code zeigt, wie die IDs von Notizelementen auf eindeutige Werte festgelegt werden.

#### F: Was passiert, wenn ich versuche, einem Notizstrukturelement eine doppelte ID zuzuweisen?

A: Der Versuch, einem Notizstrukturelement eine doppelte ID zuzuweisen, führt zu einer Ausnahme. Der im Tutorial bereitgestellte Code enthält einen Kommentar, der dieses Szenario veranschaulicht.

#### F: Wie kann ich beim Erstellen von Notizstrukturelementen die PDF/UA-Konformität sicherstellen?

 A: Der im Tutorial bereitgestellte Code zeigt, wie die PDF/UA-Konformität mithilfe von validiert wird`Validate` Methode. Durch die Validierung des Dokuments anhand des PDF/UA-Standards können Sie sicherstellen, dass die hinzugefügten Notizstrukturelemente den Barrierefreiheitsrichtlinien entsprechen.

#### F: Kann ich mit diesem Ansatz Notizstrukturelemente zu einem vorhandenen PDF-Dokument hinzufügen?

A: Ja, Sie können den bereitgestellten Ansatz ändern, um Notizstrukturelemente zu einem vorhandenen PDF-Dokument hinzuzufügen. Anstatt ein neues Dokument zu erstellen, würden Sie das vorhandene Dokument mit Aspose.PDF laden und dann ähnliche Schritte ausführen, um Notizelemente anzuhängen.
