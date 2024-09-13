---
title: Notizstrukturelement erstellen
linktitle: Notizstrukturelement erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen strukturierter Notizelemente in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 30
url: /de/net/programming-with-tagged-pdf/create-note-structure-element/
---
In diesem Tutorial erhalten Sie eine Schritt-für-Schritt-Anleitung zum Erstellen eines Notizstrukturelements in einem PDF-Dokument mit Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mit den markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie Ihrem PDF-Dokument strukturierte Notizen hinzufügen.

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

## Schritt 3: Erstellen des PDF-Dokuments und Notieren strukturierter Elemente

Verwenden Sie den folgenden Code, um ein PDF-Dokument zu erstellen und notizstrukturierte Elemente hinzuzufügen:

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

Dieser Code speichert das PDF-Dokument mit den strukturierten Elementen der Notiz in einer angegebenen Datei.

### Beispielquellcode zum Erstellen eines Notizstrukturelements mit Aspose.PDF für .NET 

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// PDF-Dokument erstellen
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
//Ausnahme muss ausgelöst werden – Aspose.Pdf.Tagged.TaggedException: Strukturelement mit ID='note_002' ist bereits vorhanden
//note3.SetId("note_002");
// Das resultierende Dokument entspricht nicht PDF/UA, wenn ClearId() für das Note Structure Element verwendet wird.
//note3.ClearId();
// Getaggtes PDF-Dokument speichern
document.Save(outFile);
// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Notizstrukturelemente in einem PDF-Dokument erstellen. Mit strukturierten Notizelementen können Sie Ihrem PDF-Dokument zusätzliche, strukturierte Informationen hinzufügen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Erstellung von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Erstellen von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET können Sie dem Inhalt des Dokuments strukturierte Notizen hinzufügen. Diese Notizen können zusätzlichen Kontext, Erklärungen oder Verweise auf bestimmte Teile des Inhalts bieten.

#### F: Wie hilft die Aspose.PDF-Bibliothek beim Erstellen von Notizstrukturelementen in einem PDF-Dokument?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die markierten Inhaltsstrukturfunktionen der Bibliothek verwendet, um strukturierte Notizelemente innerhalb des Inhalts des PDF-Dokuments zu erstellen.

#### F: Was sind die Voraussetzungen zum Erstellen von Notizstrukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Visual Studio mit dem .NET-Framework installiert haben und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code Notizstrukturelemente im Inhalt des PDF-Dokuments?

A: Der Code zeigt, wie Sie ein PDF-Dokument erstellen, strukturierte Notizelemente definieren und diese einem Absatz hinzufügen. Jede Notiz wird mit den von Aspose.PDF bereitgestellten Methoden erstellt, sodass Sie strukturierte Notizen in den Inhalt integrieren können.

#### F: Kann ich den Inhalt und die Eigenschaften der von mir erstellten Notizstrukturelemente anpassen?

A: Ja, Sie können den Inhalt und die Eigenschaften von Notizstrukturelementen anpassen, indem Sie die Methoden und Eigenschaften der Aspose.PDF-Bibliothek verwenden. Der Code zeigt, wie Sie den Text und die ID von Notizelementen festlegen, aber Sie können sie bei Bedarf weiter anpassen.

#### F: Wie wird die hierarchische Beziehung zwischen den Elementen der Notizstruktur und dem Inhalt des Dokuments hergestellt?

 A: Die hierarchische Beziehung wird hergestellt, indem Notizstrukturelemente als untergeordnete Elemente anderer strukturierter Elemente, wie z. B. Absätze, hinzugefügt werden. Im Code werden Notizelemente an ein Absatzelement angehängt, indem das`AppendChild` Verfahren.

#### F: Kann ich den Elementen der Notizstruktur eindeutige IDs zuweisen?

 A: Ja, Sie können den Notizstrukturelementen eindeutige IDs zuweisen, indem Sie`SetId` Methode. Der Code zeigt, wie die IDs von Notizelementen auf eindeutige Werte gesetzt werden.

#### F: Was passiert, wenn ich versuche, einem Notizstrukturelement eine doppelte ID zuzuweisen?

A: Der Versuch, einem Notizstrukturelement eine doppelte ID zuzuweisen, führt zu einer Ausnahme. Der im Tutorial bereitgestellte Code enthält einen Kommentar, der dieses Szenario veranschaulicht.

#### F: Wie kann ich beim Erstellen von Notizstrukturelementen die PDF/UA-Konformität sicherstellen?

A: Der im Tutorial bereitgestellte Code zeigt, wie die PDF/UA-Konformität mithilfe des`Validate` Methode. Indem Sie das Dokument anhand des PDF/UA-Standards validieren, können Sie sicherstellen, dass die hinzugefügten Notizstrukturelemente den Richtlinien zur Barrierefreiheit entsprechen.

#### F: Kann ich mit diesem Ansatz einem vorhandenen PDF-Dokument Notizstrukturelemente hinzufügen?

A: Ja, Sie können den bereitgestellten Ansatz ändern, um Notizstrukturelemente zu einem vorhandenen PDF-Dokument hinzuzufügen. Anstatt ein neues Dokument zu erstellen, laden Sie das vorhandene Dokument mit Aspose.PDF und folgen dann ähnlichen Schritten, um Notizelemente anzufügen.
