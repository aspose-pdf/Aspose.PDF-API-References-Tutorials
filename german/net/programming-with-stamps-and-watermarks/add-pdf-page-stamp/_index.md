---
title: PDF-Seitenstempel hinzufügen
linktitle: PDF-Seitenstempel hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach einen PDF-Seitenstempel zu Ihren PDF-Dokumenten hinzufügen.
type: docs
weight: 40
url: /de/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen PDF-Seitenstempel zu einem PDF-Dokument hinzufügen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einen benutzerdefinierten Stempel zu einer bestimmten Seite des PDF-Dokuments hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen des Seitenpuffers

Nachdem Sie das PDF-Dokument hochgeladen haben, können Sie den hinzuzufügenden Seitenstempel erstellen. So geht's:

```csharp
// Erstellen Sie den Seitenpuffer
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Der obige Code erstellt einen neuen Seitenpuffer unter Verwendung der ersten Seite des PDF-Dokuments.

## Schritt 4: Konfigurieren der Seitenpuffereigenschaften

Bevor Sie den Seitenstempel zum PDF-Dokument hinzufügen, können Sie verschiedene Eigenschaften des Stempels konfigurieren, wie z. B. Hintergrund, Position, Drehung usw. So geht's:

```csharp
// Konfigurieren Sie die Eigenschaften des Seitenpuffers
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen.

## Schritt 5: Hinzufügen des Seitenstempels zum PDF

Da der Seitenstempel nun fertig ist, können Sie ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
// Fügen Sie einen Seitenpuffer zu einer bestimmten Seite hinzu
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Der obige Code fügt den Seitenstempel zur ersten Seite des PDF-Dokuments hinzu. Bei Bedarf können Sie eine andere Seite angeben.

## Schritt 6: Speichern Sie das Ausgabedokument

Nachdem Sie den Seitenstempel hinzugefügt haben, können Sie das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „PDFPage Stamp hinzufügen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Seitenstempel erstellen
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Stempel zu einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen PDF-Seitenstempel hinzufügen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden, um benutzerdefinierte Stempel auf bestimmten Seiten Ihrer PDF-Dokumente hinzuzufügen.
