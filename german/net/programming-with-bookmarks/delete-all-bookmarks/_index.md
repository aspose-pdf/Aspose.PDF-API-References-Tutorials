---
title: Alle Lesezeichen löschen
linktitle: Alle Lesezeichen löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach alle Lesezeichen aus Ihren PDF-Dateien löschen.
type: docs
weight: 30
url: /de/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Löschen Sie alle Lesezeichen mit Aspose.PDF für .NET

In manchen Fällen kann es notwendig sein, Lesezeichen aus einem PDF-Dokument zu löschen. Mit Aspose.PDF für .NET können Sie alle Lesezeichen ganz einfach entfernen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie Lesezeichen entfernen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Jetzt öffnen wir das PDF-Dokument, aus dem wir die Lesezeichen entfernen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Schritt 4: Alle Lesezeichen löschen

 In diesem Schritt löschen wir mithilfe von alle Lesezeichen aus dem Dokument`Delete` Methode der`Outlines` Eigentum. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Delete();
```

## Schritt 5: Speichern Sie die aktualisierte Datei

 Abschließend speichern wir die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Alle Lesezeichen löschen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Alle Lesezeichen löschen
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Aktualisierte Datei speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Entfernen aller Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihre PDF-Dokumente bereinigen, indem Sie alle vorhandenen Lesezeichen löschen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.