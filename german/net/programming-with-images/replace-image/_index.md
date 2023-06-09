---
title: Bild ersetzen
linktitle: Bild ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ersetzen eines Bildes in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 240
url: /de/net/programming-with-images/replace-image/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Bild in einem PDF-Dokument ersetzen. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Schritt 1: Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 2: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "ReplaceImage.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 3: Ersetzen eines bestimmten Bildes

Um ein bestimmtes Bild im PDF-Dokument zu ersetzen, verwenden Sie den folgenden Code:

```csharp
// Ersetzen Sie ein bestimmtes Bild
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
```

In diesem Beispiel ersetzen wir das Bild auf Seite 1 des PDF-Dokuments. Stellen Sie sicher, dass Sie den richtigen Pfad zu dem neuen Bild angeben, das Sie verwenden möchten.

## Schritt 4: Speichern der aktualisierten PDF-Datei

Speichern Sie nach der Bildersetzung die aktualisierte PDF-Datei mit dem folgenden Code:

```csharp
dataDir = dataDir + "ReplaceImage_out.pdf";
// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved as: " + dataDir);
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für die aktualisierte PDF-Datei an.

### Beispielquellcode für „Bild ersetzen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
// Ersetzen Sie ein bestimmtes Bild
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
dataDir = dataDir + "ReplaceImage_out.pdf";
// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein Bild in einem PDF-Dokument ersetzt. Jetzt können Sie diese Methode auf Ihre eigenen Projekte anwenden, um Bilder in PDF-Dateien zu bearbeiten.