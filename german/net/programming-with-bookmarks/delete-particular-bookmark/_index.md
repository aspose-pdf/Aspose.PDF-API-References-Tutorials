---
title: Bestimmtes Lesezeichen löschen
linktitle: Bestimmtes Lesezeichen löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach ein bestimmtes Lesezeichen aus Ihren PDF-Dateien löschen.
type: docs
weight: 40
url: /de/net/programming-with-bookmarks/delete-particular-bookmark/
---

Es kann erforderlich sein, ein bestimmtes Lesezeichen aus einem PDF-Dokument zu löschen. Mit Aspose.PDF für .NET können Sie ein bestimmtes Lesezeichen ganz einfach löschen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie ein bestimmtes Lesezeichen entfernen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Jetzt öffnen wir das PDF-Dokument, aus dem wir ein Lesezeichen entfernen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Schritt 4: Löschen Sie ein bestimmtes Lesezeichen

 In diesem Schritt löschen wir ein bestimmtes Lesezeichen mit`Delete` Methode der`Outlines` Eigentum. Wir geben den Titel des zu löschenden Lesezeichens an. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Schritt 5: Speichern Sie die aktualisierte Datei

 Abschließend speichern wir die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Löschen bestimmter Lesezeichen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Löschen Sie eine bestimmte Gliederung nach Titel
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Aktualisierte Datei speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Löschen eines bestimmten Lesezeichens mit Aspose.PDF für .NET. Mit diesem Code können Sie bestimmte Lesezeichen gezielt aus Ihren PDF-Dokumenten entfernen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.