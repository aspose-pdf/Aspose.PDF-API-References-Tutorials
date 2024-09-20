---
title: PDF mit getaggtem Text erstellen
linktitle: PDF mit getaggtem Text erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem umfassenden Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET getaggte PDFs mit barrierefreiem Inhalt erstellen.
type: docs
weight: 50
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
## Einführung

Im heutigen digitalen Zeitalter sind PDF-Dokumente zu einem der beliebtesten Formate zum Teilen und Anzeigen von Inhalten geworden. Ob Geschäftsberichte, akademische Arbeiten oder Benutzerhandbücher, PDFs sind allgegenwärtig! Aber was ein gutes PDF von einem großartigen unterscheidet, sind Zugänglichkeit und Struktur. Das ist richtig! Markierte PDFs erleichtern Bildschirmlesegeräten und unterstützenden Technologien das Verstehen und Navigieren durch den Inhalt. Und wissen Sie was? In diesem Tutorial führe ich Sie Schritt für Schritt durch den Prozess der Erstellung eines markierten PDFs mit Aspose.PDF für .NET! 

Also schnappen Sie sich Ihr Lieblingsgetränk, machen Sie es sich bequem und tauchen Sie mit uns in die Welt der getaggten PDFs ein!

## Voraussetzungen

Bevor wir beginnen, müssen Sie einige Dinge vorbereitet haben:

1. Visual Studio – Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Sie können jede Version verwenden, die .NET unterstützt.
2.  Aspose.PDF für .NET - Laden Sie die neueste Version von Aspose.PDF für .NET herunter von der[Webseite](https://releases.aspose.com/pdf/net/)Sie können sich auch für eine kostenlose Testversion entscheiden, um die Funktionen kennenzulernen.
3. .NET Framework – Diese Beispiele werden für .NET erstellt. Stellen Sie sicher, dass auf Ihrem Computer eine kompatible Version installiert ist.
4. Grundkenntnisse in C# – Kenntnisse in der C#-Programmierung werden sich beim Schreiben von Code als nützlich erweisen!

Alles klar? Super! Dann legen wir los!

## Pakete importieren

Nachdem wir nun unsere Voraussetzungen geklärt haben, kommen wir zum spaßigen Teil: dem Importieren der erforderlichen Pakete. Um mit Aspose.PDF arbeiten zu können, müssen Sie die Bibliothek unbedingt zu Ihrem Projekt hinzufügen. 

### Neues Projekt erstellen

Starten Sie zunächst Visual Studio und erstellen Sie ein neues C#-Projekt.

1. Öffnen Sie Visual Studio.
2. Klicken Sie auf „Neues Projekt erstellen“.
3. Wählen Sie „Konsolen-App (.NET)“ und klicken Sie auf „Weiter“.
4.  Geben Sie Ihrem Projekt einen Namen (z. B.`TaggedPdfExample`) und legen Sie den Speicherort fest.
5. Klicken Sie auf „Erstellen“.

### Aspose.PDF-Referenz hinzufügen

Fügen wir nun die Aspose.PDF-Bibliothek hinzu:

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

### Importieren der erforderlichen Namespaces

 Oben in Ihrer Hauptprogrammdatei (wie`Program.cs`), importieren Sie die folgenden Namespaces:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem wir nun alles eingerichtet haben, zerlegen wir den Code in verdauliche Teile und erstellen Schritt für Schritt ein getaggtes PDF!

## Schritt 1: Definieren Sie das Dokumentverzeichnis

Bevor wir mit der Codierung beginnen, definieren wir das Dokumentverzeichnis, in dem wir unsere PDF-Datei speichern:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Aktualisieren Sie dies zu Ihrem Pfad
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Sie Ihre PDF-Datei speichern möchten.

## Schritt 2: Erstellen Sie ein PDF-Dokument

Lassen Sie uns eine neue PDF-Dokumentinstanz erstellen. Das ist wie das Zeichnen einer leeren Leinwand, auf der wir unseren Inhalt hinzufügen. 

```csharp
// PDF-Dokument erstellen
Document document = new Document();
```

## Schritt 3: Markierten Inhalt für das Dokument abrufen

Als nächstes müssen wir den getaggten Inhalt unseres Dokuments abrufen. Stellen Sie sich getaggten Inhalt als die zugrunde liegende Struktur vor, die es zugänglich macht. So geht's:

```csharp
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Titel und Sprache für das Dokument festlegen

Legen wir nun den Titel und die Sprache unseres Dokuments fest. Dies ist für die Barrierefreiheit äußerst wichtig!

```csharp
// Titel und Sprache für Dokument festlegen
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

## Schritt 5: Strukturelemente auf Textblockebene erstellen

Hier erstellen wir unseren Inhalt. Wir erstellen Überschriften und Absätze, genau wie Bausteine!

### Schritt 5.1: Erstellen eines Header-Elements

Lassen Sie uns zunächst ein Header-Element erstellen:

```csharp
// Erstellen von Strukturelementen auf Textblockebene
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
```

### Schritt 5.2: Absatzelemente erstellen

Als nächstes fügen wir einige Absätze hinzu. Ich werde mehrere für Sie hinzufügen, aber Sie können dies nach Ihren Bedürfnissen anpassen!

```csharp
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
```

## Schritt 6: Speichern Sie das PDF-Dokument

Zum Schluss speichern wir dieses Meisterwerk! So speichern Sie Ihr getaggtes PDF:

```csharp
// PDF-Dokument speichern
document.Save(dataDir + "PDFwithTaggedText.pdf");
```

Sie haben gerade ein getaggtes PDF erstellt! 

## Abschluss

Das Erstellen eines getaggten PDFs mit Aspose.PDF für .NET ist ein Kinderspiel, wenn Sie den Dreh erst einmal raus haben! Es macht Ihre Dokumente nicht nur benutzerfreundlich, sondern auch einem breiteren Publikum zugänglich. Die Betonung der semantischen Struktur wird sich auf jeden Fall auszahlen, insbesondere wenn Sie in Branchen tätig sind, in denen die Zugänglichkeit von Inhalten von entscheidender Bedeutung ist. 

## Häufig gestellte Fragen

### Was ist ein getaggtes PDF?  
Ein getaggtes PDF enthält strukturierte Daten, die Bildschirmlesegeräten und unterstützenden Technologien die effektive Navigation durch den Inhalt erleichtern.

### Muss ich Aspose.PDF kaufen, um es zu verwenden?  
 Sie können zwar mit einer kostenlosen Testversion beginnen, für die langfristige Nutzung ist jedoch eine Lizenz erforderlich. Weitere Informationen finden Sie hier[Hier](https://purchase.aspose.com/buy).

### Kann ich die Strukturelemente in meinem PDF anpassen?  
Auf jeden Fall! Sie können verschiedene Elemente bearbeiten und komplexe Strukturen basierend auf Ihren Anforderungen erstellen.

### Ist Aspose.PDF mit allen .NET-Anwendungen kompatibel?  
Ja, Aspose.PDF ist für die Verwendung auf verschiedenen .NET-Plattformen konzipiert, darunter .NET Framework, .NET Core und mehr.

### Wo finde ich Unterstützung für Aspose.PDF?  
 Besuchen Sie die[Aspose Support Forum](https://forum.aspose.com/c/pdf/10) für alle Fragen oder Probleme, die auftreten.