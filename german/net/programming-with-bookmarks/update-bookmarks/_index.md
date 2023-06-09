---
title: Lesezeichen aktualisieren
linktitle: Lesezeichen aktualisieren
second_title: Aspose.PDF für .NET API-Referenz
description: Aktualisieren Sie ganz einfach Lesezeichen in Ihren PDF-Dateien mit Aspose.PDF für .NET.
type: docs
weight: 100
url: /de/net/programming-with-bookmarks/update-bookmarks/
---

Das Aktualisieren von Lesezeichen in einem PDF-Dokument ist häufig erforderlich, um Änderungen oder Aktualisierungen in der Struktur oder im Inhalt des Dokuments widerzuspiegeln. Mit Aspose.PDF für .NET können Sie Lesezeichen ganz einfach aktualisieren, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie aktualisieren möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Jetzt öffnen wir das PDF-Dokument, das wir aktualisieren möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## Schritt 4: Lesezeichenobjekt abrufen

In diesem Schritt erhalten wir das spezifische Lesezeichenobjekt, das wir aktualisieren möchten. Im folgenden Beispiel rufen wir das Lesezeichen an Index 1 ab (das zweite Lesezeichen in der Lesezeichensammlung). Sie können den Index Ihren Bedürfnissen entsprechend anpassen. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Schritt 5: Lesezeicheneigenschaften aktualisieren

Jetzt aktualisieren wir die Lesezeicheneigenschaften wie Titel, Kursivschrift und Fettschrift. Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen. Hier ist der entsprechende Code:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Schritt 6: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für die Aktualisierung von Lesezeichen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Holen Sie sich ein Lesezeichenobjekt
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Aktualisieren von Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie die Titel und Stile von Lesezeichen in Ihren PDF-Dokumenten ändern.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.