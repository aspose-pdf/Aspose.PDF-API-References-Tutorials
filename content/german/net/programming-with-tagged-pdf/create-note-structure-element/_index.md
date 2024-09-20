---
title: Notizstrukturelement erstellen
linktitle: Notizstrukturelement erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem ausführlichen Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET Notizstrukturelemente in PDFs erstellen.
type: docs
weight: 30
url: /de/net/programming-with-tagged-pdf/create-note-structure-element/
---
## Einführung

Das Erstellen strukturierter Dokumente ist in der heutigen digitalen Welt unerlässlich, insbesondere beim Umgang mit PDFs. Wenn es um die Zugänglichkeit von Dokumenten geht, ist die Aspose.PDF-Bibliothek für .NET ein leistungsstarkes Tool, mit dem Entwickler PDF-Inhalte nahtlos verwalten können. In diesem Tutorial erfahren Sie ausführlich, wie Sie mit Aspose.PDF für .NET Notizstrukturelemente in einem PDF erstellen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Anleitung führt Sie in einer verständlichen und leicht verständlichen Art und Weise durch jeden Schritt. Also, legen wir los!

## Voraussetzungen

Bevor wir uns in die Codierung und Erstellung von Notizstrukturelementen stürzen, stellen wir sicher, dass Sie alles Nötige bereit haben:

1. .NET-Umgebung: Sie sollten eine .NET-Entwicklungsumgebung wie Visual Studio eingerichtet haben.
2.  Aspose.PDF-Bibliothek: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie finden sie unter[Hier](https://releases.aspose.com/pdf/net/).
3. Grundlegende C#-Kenntnisse: Um dieses Tutorial optimal nutzen zu können, sind Kenntnisse in der C#-Programmierung erforderlich.
4. Zugriff auf .NET Framework: Stellen Sie sicher, dass Ihr Projekt auf eine kompatible Version des .NET Frameworks abzielt.
5. Dokumentverzeichnis: Richten Sie ein Verzeichnis zum Speichern Ihrer PDF- und Protokolldateien ein. 

Alles bereit? Super! Dann stürzen wir uns auf den Code!

## Pakete importieren

Der erste Schritt besteht darin, die erforderlichen Pakete zu importieren. Dies kann in Ihrer Entwicklungsumgebung erfolgen. Hier ist eine einfache Möglichkeit, dies zu tun:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die zum Erstellen und Bearbeiten von PDF-Dokumenten erforderlich sind.

## Schritt 1: Einrichten des Dokuments

Zu Beginn müssen Sie eine neue Dokumentinstanz erstellen. Dies ist der Ausgangspunkt für jedes PDF, das Sie generieren möchten. So gehen Sie vor:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

// PDF-Dokument erstellen
Document document = new Document();
```
Dieser Code initialisiert eine neue`Document` Objekt und richtet Dateipfade für die Ausgabe-PDF- und Protokolldateien ein. Stellen Sie sicher, dass Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch Ihren tatsächlichen Verzeichnispfad.

## Schritt 2: Festlegen von Tagged Content-Attributen

Als Nächstes richten wir den getaggten Inhalt für Ihr PDF ein. Dazu gehört das Definieren der Titel- und Sprachattribute.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
```
 Hier greifen wir auf die`TaggedContent` des Dokuments und Festlegen von Titel und Sprache. Dies ist für die Zugänglichkeitsstandards von entscheidender Bedeutung und verleiht Ihrem Dokument einen professionelleren Touch.

## Schritt 3: Erstellen eines Absatzelements

Jetzt fügen wir dem getaggten Inhalt ein Absatzelement hinzu. Dieses dient als Container für Ihre Notizen.

```csharp
// Absatzelement hinzufügen
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
```
 Durch die Schaffung einer`ParagraphElement`, wir stellen eine Basis bereit, zu der Notizelemente hinzugefügt werden. Es ist vergleichbar mit dem Legen des Fundaments für ein Haus, bevor die Wände gebaut werden.

## Schritt 4: Notizelemente hinzufügen

Jetzt kommt der spaßige Teil: Notizelemente hinzufügen! Sie können mehrere Notizen erstellen – machen wir das in drei Schritten!

### Schritt 4.1: Die erste Note hinzufügen

```csharp
// NoteElement hinzufügen
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID.");
```
Dieser Code erstellt die erste Notiz mit einer automatisch generierten ID. Beachten Sie, wie einfach es ist, unserem vorherigen Absatz Inhalt hinzuzufügen.

### Schritt 4.2: Die zweite Note hinzufügen

```csharp
// NoteElement hinzufügen
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
```
 Für die zweite Notiz setzen wir explizit eine ID von`note_002`. Achten Sie unbedingt auf die IDs, da Sie damit später auf bestimmte Notizen verweisen können.

### Schritt 4.3: Dritte Note hinzufügen

```csharp
// NoteElement hinzufügen
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Ausnahme muss ausgelöst werden – Aspose.Pdf.Tagged.TaggedException: Strukturelement mit ID='note_002' ist bereits vorhanden
```
 Diese dritte Notiz ist der zweiten sehr ähnlich, verwendet aber eine andere eindeutige ID. Seien Sie vorsichtig; der Versuch, eine weitere Notiz mit derselben ID zu erstellen wie`note_002` wird eine Ausnahme auslösen. 

## Schritt 5: Speichern des Dokuments

Sobald Sie Ihre Notizen hinzugefügt haben, ist es Zeit, das Dokument zu speichern!

```csharp
// Getaggtes PDF-Dokument speichern
document.Save(outFile);
```
Diese einfache Zeile speichert Ihre gesamte harte Arbeit in der angegebenen PDF-Datei. 

## Schritt 6: PDF/UA-Konformität validieren

Um sicherzustellen, dass Ihr Dokument den Barrierefreiheitsstandards entspricht, können Sie es validieren.

```csharp
// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```
Dieser Codeabschnitt prüft Ihr PDF auf den PDF/UA-Standard (Universal Accessibility). Sie erhalten einen booleschen Wert, der die Konformität anzeigt!

## Abschluss

Und da haben Sie es! Sie haben jetzt erfolgreich Notizstrukturelemente in einem PDF-Dokument erstellt, die eine bessere Zugänglichkeit und Struktur ermöglichen – dank Aspose.PDF für .NET! Indem Sie diese Schritte befolgen, können Sie Ihre PDFs effizienter verwalten und benutzerfreundlicher gestalten. 

## Häufig gestellte Fragen

### Was sind Notizstrukturelemente in PDFs?
Notizelemente sind Anmerkungen oder Kommentare, die zu bestimmten Teilen einer PDF-Datei hinzugefügt werden, um die Klarheit und das Verständnis zu verbessern.

### Ist Aspose.PDF für .NET kostenlos?
Obwohl eine kostenlose Testversion angeboten wird, handelt es sich bei Aspose.PDF um ein kommerzielles Produkt. Die Preise variieren je nach Nutzung und erforderlichen Funktionen.

### Kann ich mit Aspose.PDF andere Elementtypen erstellen?
Ja! Aspose.PDF unterstützt zahlreiche Elemente wie Bilder, Tabellen und Hyperlinks, um Ihre Dokumente zu bereichern.

### Was ist PDF/UA-Konformität?
Durch die PDF/UA-Konformität wird sichergestellt, dass PDFs für Personen mit Behinderungen zugänglich sind und globalen Standards entsprechen.

### Wo erhalte ich Support für Aspose.PDF?
 Für Unterstützung besuchen Sie die[Aspose-Forum](https://forum.aspose.com/c/pdf/10) wo Sie Fragen stellen und Ihre Erfahrungen austauschen können.