---
title: Lesezeichen hinzufügen
linktitle: Lesezeichen hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Lesezeichen zu Ihren PDF-Dateien hinzu, um die Navigation zu verbessern.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/add-bookmark/
---

Das Hinzufügen von Lesezeichen in einem PDF-Dokument ermöglicht eine einfache und schnelle Navigation. Mit Aspose.PDF für .NET können Sie ganz einfach ein Lesezeichen hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, der Sie ein Lesezeichen hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir ein Lesezeichen hinzufügen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Schritt 4: Lesezeichenobjekt erstellen

 In diesem Schritt erstellen wir ein Lesezeichenobjekt mit`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften wie Titel, Kursivschrift-Attribut, Fettdruck-Attribut und Aktion fest, die beim Klicken ausgeführt werden soll. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Schritt 5: Lesezeichen zum Dokument hinzufügen

 Abschließend fügen wir das erstellte Lesezeichen mithilfe von zur Lesezeichensammlung des Dokuments hinzu`Add` Methode der`Outlines` Eigentum. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Beispielquellcode für „Lesezeichen hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Erstellen Sie ein Lesezeichenobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Legen Sie die Zielseitennummer fest
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Fügen Sie der Gliederungssammlung des Dokuments ein Lesezeichen hinzu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Hinzufügen eines Lesezeichens mit Aspose.PDF für .NET. Mit diesem Code können Sie die Navigation in Ihren PDF-Dokumenten verbessern, indem Sie benutzerdefinierte Lesezeichen hinzufügen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.