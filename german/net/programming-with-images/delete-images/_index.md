---
title: Bilder löschen
linktitle: Bilder löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie Bilder ganz einfach aus einer PDF-Datei löschen.
type: docs
weight: 110
url: /de/net/programming-with-images/delete-images/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Bilder aus einer PDF-Datei löschen. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Schritt 3: Löschen Sie ein bestimmtes Bild

 In diesem Schritt löschen wir ein bestimmtes Bild von einer bestimmten Seite. Benutzen Sie die`Delete` Methode der Seitenressource`Images` Objekt, um das Bild zu löschen. Im folgenden Beispiel löschen wir das Bild mit Index 1 von der ersten Seite.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Schritt 4: Speichern Sie die aktualisierte PDF-Datei

 Speichern Sie die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Löschen von Bildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Ein bestimmtes Bild löschen
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder aus einer PDF-Datei gelöscht. Die aktualisierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei jetzt ohne die gelöschten Bilder verwenden.