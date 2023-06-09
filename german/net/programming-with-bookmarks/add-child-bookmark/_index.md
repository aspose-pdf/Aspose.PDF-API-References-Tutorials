---
title: Untergeordnetes Lesezeichen hinzufügen
linktitle: Untergeordnetes Lesezeichen hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach untergeordnete Lesezeichen zu Ihren PDF-Dateien hinzu, um das Durchsuchen besser zu organisieren.
type: docs
weight: 20
url: /de/net/programming-with-bookmarks/add-child-bookmark/
---

Das Hinzufügen untergeordneter Lesezeichen zu einem PDF-Dokument ermöglicht eine strukturiertere Organisation und Navigation. Mit Aspose.PDF für .NET können Sie ganz einfach ein Unterlesezeichen hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, der Sie ein Unterlesezeichen hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir ein Unterlesezeichen hinzufügen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Schritt 4: Erstellen Sie ein übergeordnetes Lesezeichenobjekt

 In diesem Schritt erstellen wir mithilfe von ein übergeordnetes Lesezeichenobjekt`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften wie Titel, Kursivschrift-Attribut und Fettdruck-Attribut fest. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Schritt 5: Erstellen Sie ein untergeordnetes Lesezeichenobjekt

In diesem Schritt erstellen wir erneut ein Unter-Lesezeichen-Objekt mit`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften fest. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Schritt 6: Fügen Sie das Unter-Lesezeichen zum übergeordneten Lesezeichen hinzu

 Schließlich fügen wir das erstellte Unterlesezeichen mithilfe von zur Unterlesezeichensammlung des übergeordneten Lesezeichens hinzu`Add` Methode des übergeordneten Objekts. Hier ist der entsprechende Code:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Schritt 7: Fügen Sie das übergeordnete Lesezeichen zur Lesezeichensammlung des Dokuments hinzu

 Schließlich fügen wir das übergeordnete Lesezeichen mithilfe von zur Lesezeichensammlung des Dokuments hinzu`Add` Methode der`Outlines` Eigentum. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Beispielquellcode für „Untergeordnetes Lesezeichen hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Erstellen Sie ein übergeordnetes Lesezeichenobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Erstellen Sie ein untergeordnetes Lesezeichenobjekt
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Fügen Sie ein untergeordnetes Lesezeichen zur Sammlung des übergeordneten Lesezeichens hinzu
pdfOutline.Add(pdfChildOutline);
// Fügen Sie der Gliederungssammlung des Dokuments ein übergeordnetes Lesezeichen hinzu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Hinzufügen eines Unterlesezeichens mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihre Lesezeichen in Ihren PDF-Dokumenten organisieren und strukturieren.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.