---
title: Ausrichtung definieren
linktitle: Ausrichtung definieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach die Textausrichtung in Ihren PDF-Dokumenten festlegen.
type: docs
weight: 70
url: /de/net/programming-with-stamps-and-watermarks/define-alignment/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET die Textausrichtung in einem PDF-Dokument festlegen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einen zentrierten Textstempel im PDF-Dokument erstellen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie ein Document-Objekt mit der Eingabedatei
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Definieren der Ausrichtung

Nachdem Sie nun das PDF-Dokument geladen haben, können Sie die Ausrichtung des Textstempels festlegen. Hier ist wie:

```csharp
// Instanziieren Sie ein FormattedText-Objekt mit der Beispielzeichenfolge
FormattedText text = new FormattedText("This");

// Fügen Sie FormattedText eine neue Textzeile hinzu
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// Erstellen Sie ein TextStamp-Objekt mit FormattedText
TextStamp stamp = new TextStamp(text);

// Geben Sie die horizontale Ausrichtung des Textpuffers als zentriert an
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Geben Sie die vertikale Ausrichtung des Textpuffers als zentriert an
stamp.VerticalAlignment = VerticalAlignment.Center;

// Geben Sie die horizontale Ausrichtung des Texts im TextStamp als zentriert an
stamp.TextAlignment = HorizontalAlignment.Center;

// Legen Sie den oberen Rand für das Pufferobjekt fest
stamp. TopMargin = 20;

// Fügen Sie das Stempelobjekt zur ersten Seite des Dokuments hinzu
doc.Pages[1].AddStamp(stamp);
```

Der obige Code erstellt einen zentrierten Textpuffer mithilfe der FormattedText-Klasse, um den Inhalt anzugeben und die horizontale und vertikale Ausrichtung des Textpuffers festzulegen.

## Schritt 4: Speichern Sie das Ausgabedokument

Sobald Sie die Ausrichtung des Textstempels festgelegt haben, können Sie das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für „Ausrichtung definieren“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Instanziieren Sie das Dokumentobjekt mit der Eingabedatei
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Instanziieren Sie das FormattedText-Objekt mit der Beispielzeichenfolge
FormattedText text = new FormattedText("This");

// Fügen Sie FormattedText eine neue Textzeile hinzu
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// Erstellen Sie ein TextStamp-Objekt mit FormattedText
TextStamp stamp = new TextStamp(text);

// Geben Sie die horizontale Ausrichtung des Textstempels als „Mittig ausgerichtet“ an
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Geben Sie die vertikale Ausrichtung des Textstempels als „Mittig ausgerichtet“ an
stamp.VerticalAlignment = VerticalAlignment.Center;

// Geben Sie die horizontale Textausrichtung von TextStamp als „Mittig ausgerichtet“ an
stamp.TextAlignment = HorizontalAlignment.Center;

// Legen Sie den oberen Rand für das Stempelobjekt fest
stamp.TopMargin = 20;

// Fügen Sie das Stempelobjekt über der ersten Seite des Dokuments hinzu
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET die Textausrichtung in einem PDF-Dokument festlegen. Dieses Wissen können Sie nun anwenden, um Textstempel mit unterschiedlichen Ausrichtungen in Ihren PDF-Dokumenten zu erstellen.
