---
title: Untergeordnete Lesezeichen aktualisieren
linktitle: Untergeordnete Lesezeichen aktualisieren
second_title: Aspose.PDF für .NET API-Referenz
description: Aktualisieren Sie untergeordnete Lesezeichen in Ihren PDF-Dateien ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/programming-with-bookmarks/update-child-bookmarks/
---

Durch das Aktualisieren untergeordneter Lesezeichen in einem PDF-Dokument können Sie die Eigenschaften bestimmter Lesezeichen innerhalb eines übergeordneten Lesezeichens ändern. Mit Aspose.PDF für .NET können Sie untergeordnete Lesezeichen einfach aktualisieren, indem Sie dem folgenden Quellcode folgen:

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
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Schritt 4: Übergeordnetes Lesezeichenobjekt abrufen

In diesem Schritt rufen wir das spezifische übergeordnete Lesezeichenobjekt ab, dessen untergeordnete Lesezeichen wir aktualisieren möchten. Im folgenden Beispiel rufen wir das übergeordnete Lesezeichen an Index 1 ab (das zweite Lesezeichen in der Lesezeichensammlung). Sie können den Index Ihren Bedürfnissen entsprechend anpassen. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Schritt 5: Untergeordnetes Lesezeichenobjekt abrufen

Lassen Sie uns nun das spezifische untergeordnete Lesezeichenobjekt abrufen, das wir aktualisieren möchten. Im folgenden Beispiel rufen wir das untergeordnete Lesezeichen an Index 1 ab (das zweite untergeordnete Lesezeichen in der Sammlung untergeordneter Lesezeichen des übergeordneten Lesezeichens). Sie können den Index Ihren Bedürfnissen entsprechend anpassen. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Schritt 6: Aktualisieren Sie die Eigenschaften untergeordneter Lesezeichen

Jetzt aktualisieren wir die Eigenschaften des untergeordneten Lesezeichens wie Titel, Kursivschrift und Fettschrift. Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen. Hier ist der entsprechende Code:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Schritt 7: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für die Aktualisierung untergeordneter Lesezeichen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Holen Sie sich ein Lesezeichenobjekt
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Untergeordnetes Lesezeichenobjekt abrufen
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Aktualisieren untergeordneter Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie die Eigenschaften untergeordneter Lesezeichen in Ihren PDF-Dokumenten ändern.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.